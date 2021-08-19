```css
               ._content
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
        <div class="webgl-content _content">
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

```js
        function _progress_(x)
        {
                let _load = Math.floor(x * 100).toString() + "%";
                if (x == 1)
                {
                        document.querySelector("._BOX_0_0_0_0").style.width = (x * 100).toString() + "%";
                        document.querySelector("._BOX_0_0_0_0").setAttribute("_attr", _load);
                        document.querySelector("._BOX_0_0_1_0").innerHTML = "loading... " + x.toFixed(2).toString();
                        setTimeout(function()
                        {
                                document.querySelector("._BOX_0").style.display = "none";
                        }, 50);
                        //
                }
                else
                {
                        document.querySelector("._BOX_0_0_0_0").style.width = (x * 100).toString() + "%";
                        document.querySelector("._BOX_0_0_0_0").setAttribute("_attr", _load);
                        document.querySelector("._BOX_0_0_1_0").innerHTML = "loading... " + x.toFixed(2).toString();
                }
        }

```


<br>
<br>
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


            //.......................
            //            gameInstance.container.appendChild(gameInstance.logo);
            //.......................

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


            //.......................
            //          gameInstance.container.appendChild(gameInstance.progress);
            //.......................


      }



      //.......................
      _progress_(progress);
      //.......................




      gameInstance.progress.full.style.width = (100 * progress) + "%";
      gameInstance.progress.empty.style.width = (100 * (1 - progress)) + "%";
      if (progress == 1)
            gameInstance.logo.style.display = gameInstance.progress.style.display = "none";
}

```

<br>
<br>
<br>
<br>


![alt_txt](WEBGL_CANVAS_0_1_LOADING.PNG)

```css
                ._BOX_0
                {
                        position: absolute;
                        width: 100vw;
                        height: 100vh;
                        background-color: rgba(0, 0, 0, 0.3);

                        margin: 0px;
                        padding: 0px;
                        left: 0px;
                        top: 0px;

                        z-index: 100;

                        display: flex;
                        justify-content: center;
                        align-items: center;


                        --a: #333;
                        --b: #444;
                        --c: #ddd;
                        --d: #444;
                        --e: #eee;
                }

                ._BOX_0_0
                {
                        width: 30vw;
                        min-width: 12rem;
                        max-width: 18rem;
                        height: 7rem;
                        background-color: var(--a);

                        border-radius: 2px;
                        display: flex;
                        justify-content: center;
                        flex-direction: column;

                        transform: translate(0px, -20%);
                }


                ._BOX_0_0_0
                {
                        height: 0.7rem;
                        margin: 0.4rem;
                        width: calc(100%-1rem);

                        background-color: var(--b);
                        border-radius: 1px;
                }

                /**/
                ._BOX_0_0_0_0
                {
                        height: 100%;
                        width: 20%;
                        background-color: var(--c);

                        /*
                        --_a: hsla(120, 00%, 100%, 1);
                        --_b: hsla(360, 50%, 50%, 1);
                        background: repeating-linear-gradient
                        (
                        -45deg,
                        var(--_a) 0,
                        var(--_a) 5px,
                        var(--_b) 5px,
                        var(--_b) 12px
                        );
                        */
                        border-right: 2px solid #eee;
                        position: relative;
                }

                ._BOX_0_0_0_0::after
                {
                        content: attr(_attr);
                        width: 2.2rem;
                        /*  height: 0.8rem;*/

                        background: #bbb;
                        color: #111;
                        position: absolute;
                        right: -1px;
                        top: 0px;
                        transform: translate(0px, calc(-100% - 2px));

                        padding: 1px 2px;
                        margin: 0px;

                        font-family: monospace;
                        font-weight: bold;
                        font-size: 0.7rem;
                        text-align: center;

                        --_bevel: 4px;
                        clip-path: polygon(var(--_bevel) 0px, 100% 0px,
                                        100% calc(100% - var(--_bevel)),
                                        calc(100% - var(--_bevel)) 100%,
                                        0% 100%, 0% var(--_bevel));
                }


                ._BOX_0_0_1
                {
                        height: 5rem;
                        margin: 0.5rem;
                        width: calc(100%-1rem);
                        background-color: var(--d);

                        border-radius: 1px;

                        display: flex;
                        justify-content: center;
                        align-items: center;
                }

                /**/
                ._BOX_0_0_1_0
                {
                        background-color: var(--d);
                        border-radius: 3px;

                        color: var(--e);
                        padding: 0.2rem 0.5rem 0.2rem 0.5rem;


                        font-family: consolas;
                        font-weight: bolder;
                        font-size: 0.8rem;

                }


```




```html

        <div class="_BOX_0">
                <div class="_BOX_0_0">
                        <div class="_BOX_0_0_0">
                                <div class="_BOX_0_0_0_0" _attr="0%">
                                </div>
                        </div>
                        <div class="_BOX_0_0_1">
                                <div class="_BOX_0_0_1_0">
                                        loading... 0.12
                                </div>
                        </div>
                </div>
        </div>

```


















