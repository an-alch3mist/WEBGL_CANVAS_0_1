```css
                .webgl-content
                {
                        transform: none !important;
                        left: 0px !important;
                        top: 0px !important;
                }

                ._container
                {
                        width: 100vw !important;
                        height: 100vh !important;

                        overflow: hidden !important;
                        display: flex !important;
                        justify-content: center;
                        align-items: center !important;
                        background-color: #000 !important;
                }

                canvas
                {

                        width: 100vw !important;
                        /* max-width: 80rem !important; */
                        height: calc(100vw * 0.42) !important;
                        display: block !important;
                        background-color: #222 !important;
                }

                ._hide
                {
                        display: none !important;
                }

```

<br>


```html
        <div class="webgl-content">
                <div id="gameContainer" class="_container" style="width: 1000px; height: 300px">


                </div>

                <div class="footer _hide">
                        <div class="webgl-logo"></div>
                        <div class="fullscreen" onclick="gameInstance.SetFullscreen(1)"></div>
                        <div class="title">IO_web_1_1</div>
                </div>
        </div>

```

<br>
<br>
<br>
```html
        <script type="text/javascript">
                function _progress_(x)
                {
                        if (x == 1)
                        {
                                document.querySelector("._BOX_0_0_0_0").style.width = (x * 100).toString() + "%";

                                setTimeout(function()
                                {
                                        document.querySelector("._BOX_0").style.display = "none";
                                }, 50);

                                //


                        }
                        else
                        {
                                document.querySelector("._BOX_0_0_0_0").style.width = (x * 100).toString() + "%";

                        }
                }

        </script>

```


<br>
<br>

```js
function UnityProgress(gameInstance, progress)
{
      if (!gameInstance.Module)
            return;

      if (!gameInstance.logo)
      {
            gameInstance.logo = document.createElement("div");
            gameInstance.logo.className = "logo " + gameInstance.Module.splashScreenStyle;

            //            gameInstance.container.appendChild(gameInstance.logo);


      }

      if (!gameInstance.progress)
      {
            gameInstance.progress = document.createElement("div");
            gameInstance.progress.className = "progress " + gameInstance.Module.splashScreenStyle;
            gameInstance.progress.empty = document.createElement("div");
            gameInstance.progress.empty.className = "empty";
            gameInstance.progress.appendChild(gameInstance.progress.empty);
            gameInstance.progress.full = document.createElement("div");
            gameInstance.progress.full.className = "full";

            gameInstance.progress.appendChild(gameInstance.progress.full);

            //          gameInstance.container.appendChild(gameInstance.progress);

      }

      //
      _progress_(progress);
      //


      gameInstance.progress.full.style.width = (100 * progress) + "%";
      gameInstance.progress.empty.style.width = (100 * (1 - progress)) + "%";
      if (progress == 1)
            gameInstance.logo.style.display = gameInstance.progress.style.display = "none";
}

```
