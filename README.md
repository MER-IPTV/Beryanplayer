<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body, html { margin: 0; padding: 0; height: 100%; width: 100%; display: flex; justify-content: center; align-items: center; background-color: #050509; font-family: sans-serif; }
        .bg { position: absolute; width: 100%; height: 100%; background: radial-gradient(circle, rgba(0,210,255,0.1) 0%, rgba(5,5,9,1) 80%); z-index: 1; }
        .play-btn { position: relative; z-index: 10; width: 100px; height: 100px; border: 2px solid #00d2ff; border-radius: 50%; display: flex; justify-content: center; align-items: center; cursor: pointer; background: transparent; }
        .play-btn::after { content: ''; width: 0; height: 0; border-top: 15px solid transparent; border-bottom: 15px solid transparent; border-left: 25px solid #00d2ff; margin-left: 8px; }
        
        /* تصميم الرسالة المماثل للصورة */
        .modal { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.7); display: none; justify-content: center; align-items: center; z-index: 100; }
        .modal-box { background: #333333; width: 85%; max-width: 400px; border-radius: 4px; box-shadow: 0 5px 15px rgba(0,0,0,0.5); overflow: hidden; color: white; }
        .modal-content { padding: 24px; }
        .modal-title { font-size: 22px; font-weight: bold; margin-bottom: 15px; text-align: left; }
        .modal-body { font-size: 18px; line-height: 1.5; margin-bottom: 10px; color: #e0e0e0; text-align: center; }
        .modal-actions { display: flex; justify-content: flex-end; padding: 8px; gap: 10px; }
        .btn-action { background: transparent; border: none; color: #fff; padding: 10px 15px; cursor: pointer; font-size: 16px; font-weight: bold; text-transform: uppercase; text-decoration: none; }
        .btn-action:hover { background: rgba(255,255,255,0.1); }
    </style>
</head>
<body>
    <div class="bg"></div>
    <div class="play-btn" onclick="launch()"></div>

    <div id="m" class="modal">
        <div class="modal-box">
            <div class="modal-content">
                <div class="modal-title">Important</div>
                <div class="modal-body">
                    عليك بتحديث تطبيق المشغل لمشاهدة القنوات
                    <br><br>
                    You have to Update the YTV Player Pro app to play the channels.
                </div>
            </div>
            <div class="modal-actions">
                <button class="btn-action" onclick="document.getElementById('m').style.display='none'">CLOSE</button>
                <a href="https://play.google.com/store/apps/details?id=com.btv.video.player" class="btn-action">GET APP</a>
            </div>
        </div>
    </div>

    <script>
    function launch(){
        const start = Date.now();
        window.location.href = "intent://bsr_player_exoW3sibmFtZV9zZXJ2ZXIiOiLYs9mE2LPZhCIsInVybF9jaGFubmVsIjoiaHR0cHM6Ly9zaGQtZ2NwLWxpdmUuZWRnZW5leHRjZG4ubmV0L2xpdmUvYml0bW92aW4tbWJjLW1hc3ItMi83NTQ5MzE4NTY1MTUwNzViMGFhYmYwZTU4MzQ5NWM2OC9pbmRleC5tM3U4IiwidXNlckFnZW50IjoiIiwicmVmZXJlciI6IiIsImRybV9rZXkiOiIiLCJvcmlnaW4iOiIiLCJ0eXBlX3BsYXllciI6ImJzcl9wbGF5ZXJfZXhvIn1d#Intent;scheme=xmtv;package=com.btv.video.player;end";
        setTimeout(function(){ 
            if(Date.now() - start < 1500) {
                document.getElementById('m').style.display = 'flex';
            }
        }, 1000);
    }
    </script>
</body>
</html>
