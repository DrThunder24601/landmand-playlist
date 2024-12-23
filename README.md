# landmand-playlist
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Continuous Video Playlist</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #000;
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        video {
            max-width: 100%;
            max-height: 100%;
        }
    </style>
</head>
<body>
    <video id="videoPlayer" controls autoplay></video>

    <script>
        // Array of Google Drive embed links for your videos
        const videoUrls = [
            "https://drive.google.com/uc?id=1JRtXXnHWR6cHisvhHjmzubHBN9pZzuiG&export=download",
            "https://drive.google.com/uc?id=1E8e1ibBpIinktx_A5IuKs_oPMa8uoI1Q&export=download",
            "https://drive.google.com/uc?id=1sQc0YsaJxM00LU8C8rWAwvbf5y-f5Uc_&export=download",
            "https://drive.google.com/uc?id=1vamMfs2BXUKRWTs1xfn7wA7e7omnQxdj&export=download",
            "https://drive.google.com/uc?id=1rWoTucyW-mH0yAGLsxntemXZ__O0boG2&export=download",
            "https://drive.google.com/uc?id=1MltbfxWO9mi0C-TiaRWD7woxDM1ONDPy&export=download",
            "https://drive.google.com/uc?id=1_Q0PV1err77ZdGHQnYQzcIkcEO7uLAEY&export=download",
            "https://drive.google.com/uc?id=1tZmSG3hjJjnivL4VE-3HrWTdSv6bqvRU&export=download",
            "https://drive.google.com/uc?id=1ny9_3qyn72PFi7tBn7VYhdaeRDzdhlJF&export=download"
        ];

        const videoPlayer = document.getElementById('videoPlayer');
        let currentVideoIndex = 0;

        // Load the first video
        function loadVideo(index) {
            videoPlayer.src = videoUrls[index];
            videoPlayer.play();
        }

        // Event listener to load the next video when the current one ends
        videoPlayer.addEventListener('ended', () => {
            currentVideoIndex = (currentVideoIndex + 1) % videoUrls.length;
            loadVideo(currentVideoIndex);
        });

        // Initialize the player
        loadVideo(currentVideoIndex);
    </script>
</body>
</html>
