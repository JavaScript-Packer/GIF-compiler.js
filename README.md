# GIF-compiler.js
Demo: http://codepen.io/samples/pen/OVeEgj It generates animated GIF images (or grab a snapshot) from external static images, videos or your webcam VIA JavaScript. It is a modded version of https://github.com/yahoo/gifshot

SAMPLES OF USAGE:

```javascript
gifshot.createGIF({
    gifWidth: 444,
    gifHeight: 333,
    images: [
        'http://i.imgur.com/2OO33vX.jpg',
        'http://i.imgur.com/qOwVaSN.png',
        'http://i.imgur.com/Vo5mFZJ.gif'
    ],
    interval: .001,
    numFrames: 3,
    text: 'www.WHAK.com',
    fontWeight: 'bold',
    fontSize: '28px',
    fontFamily: 'Arial',
    fontColor: 'yellow',
    textAlign: 'center',
    textBaseline: 'center',
    sampleInterval: 1,
    numWorkers: 10
}, function (obj) {
    if (!obj.error) {
        var image = obj.image, animatedImage = document.createElement('img');
        animatedImage.src = image;
        document.body.appendChild(animatedImage);
    }
});
}()


//from webcam
gifshot.createGIF({}, function (obj) {
    if (!obj.error) {
        var image = obj.image, animatedImage = document.createElement('img');
        animatedImage.src = image;
        document.body.appendChild(animatedImage);
    }
});


//from video
gifshot.createGIF({
    video: [
        'example.mp4',
        'example.ogv'
    ]
}, function (obj) {
    if (!obj.error) {
        var image = obj.image, animatedImage = document.createElement('img');
        animatedImage.src = image;
        document.body.appendChild(animatedImage);
    }
});


//just grab a snapshot
gifshot.takeSnapShot({
    video: [
        'example.mp4',
        'example.ogv'
    ]
}, function (obj) {
    if (!obj.error) {
        var image = obj.image, animatedImage = document.createElement('img');
        animatedImage.src = image;
        document.body.appendChild(animatedImage);
    }
});
