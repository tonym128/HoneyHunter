# HoneyHunter
Honey Hunter Game for ESP32 TTGO T-Display Platform IO

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Squeezelite-ESP32 installer</title>
    <meta
      name="description"
      content="Easily allow users to install Squeezelite-ESP32 firmware on the web."
    />
    <meta name="viewport" content="width=device-width" />
    <meta name="color-scheme" content="dark light" />
    <style>
      body {
        font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI",
          Roboto, Ubuntu, sans-serif;
        padding: 0;
        margin: 0;
        line-height: 1.4;
      }
      .content {
        max-width: 600px;
        margin: 0 auto;
        padding: 12px;
      }
      h2 {
        margin-top: 2em;
      }
      h3 {
        margin-top: 1.5em;
      }
      a {
        color: #03a9f4;
      }
      .invisible {
        visibility: hidden;
      }
      .hidden {
        display: none;
      }
      esp-web-install-button[install-unsupported] {
        visibility: inherit;
      }
      .content pre {
        max-width: 100%;
        overflow-y: scroll;
      }
      .footer {
        margin-top: 24px;
        border-top: 1px solid #ccc;
        padding-top: 24px;
        text-align: center;
      }
      .footer .initiative {
        font-style: italic;
        margin-top: 16px;
      }
      table {
        border-spacing: 0;
      }
      td {
        padding: 8px;
        border-bottom: 1px solid #ccc;
      }
      .radios li {
        list-style: none;
        line-height: 2em;
      }
      @media (prefers-color-scheme: dark) {
        body {
          background-color: #333;
          color: #fff;
        }
        a {
          color: #58a6ff;
        }
      }
    </style>
    <script type="module" src="https://unpkg.com/esp-web-tools@8.0.1/dist/web/install-button.js?module"></script>
  </head>
  <body>
    <div class="content">
      <h1>Squeezelite-ESP32 installer</h1>
      <p>Select your product</p>
      <ul class="radios">
        <li>
          <label><input type="radio" name="type" value="i2s" /> I2S</label>
        </li>
        <li>
          <label><input type="radio" name="type" value="muse" /> Muse</label>
        </li>
        <li>
          <label><input type="radio" name="type" value="muse_proto" /> Muse Proto</label>
        </li>
        <li>
          <label><input type="radio" name="type" value="squeezeamp" /> SqueezeAmp</label>
        </li>
      </ul>
      <p class="button-row" align="center">
        <esp-web-install-button class="invisible"></esp-web-install-button>
      </p>

      <div class="footer">
        <a href="https://github.com/sle118/squeezelite-esp32"
          >Squeezelite-ESP32</a
        > &mdash;
        Installer powered by <a href="https://esphome.github.io/esp-web-tools/">ESP Web Tools</a>.
    </div>
    <script>
      document.querySelectorAll('input[name="type"]').forEach(radio =>
        radio.addEventListener("change", () => {
          const button = document.querySelector('esp-web-install-button');
          button.manifest = `./manifest_${radio.value}.json`;
          button.classList.remove('invisible');
        }
      ));
    </script>
  </body>
</html>
