[<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Embed M3U8 Stream</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        #videoPlayer {
            max-width: 100%;
            height: auto;
            border: 2px solid #ccc;
            border-radius: 8px;
        }
    </style>
</head>
<body>
    <video id="videoPlayer" controls width="640" height="360">
        Seu navegador não suporta a tag de vídeo HTML5.
    </video>

    <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
    <script>
        if (Hls.isSupported()) {
            var video = document.getElementById('videoPlayer');
            var hls = new Hls();
            // Usando o AllOrigins para contornar o problema CORS
            var proxyUrl = 'https://api.allorigins.win/raw?url=';
            var streamUrl = 'http://dns.topplay.top:80/live/Leonardo77/983469871/871002.m3u8';
            hls.loadSource(proxyUrl + encodeURIComponent(streamUrl));
            hls.attachMedia(video);
            hls.on(Hls.Events.MANIFEST_PARSED, function() {
                video.play();
            });
        } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
            // Usando o AllOrigins para contornar o problema CORS
            video.src = 'https://api.allorigins.win/raw?url=' + encodeURIComponent('http://dns.topplay.top:80/live/Leonardo77/983469871/871002.m3u8');
            video.addEventListener('loadedmetadata', function() {
                video.play();
            });
        }
    </script>
</body>
</html>
](https://balofa5423.balofa5423.workers.dev/espn4/tracks-v1a1/mono.m3u8)
