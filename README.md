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
