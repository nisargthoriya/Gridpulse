GridPulse - front-end for Zoho Catalyst Slate
=============================================

Contents
  index.html   The complete GridPulse dashboard (single self-contained page).

Deploy on Catalyst Slate (console upload)
  1. Catalyst console -> your project -> Slate -> Create App / Deploy.
  2. Choose "Upload", framework "Static / Basic HTML", no build command.
  3. Upload this zip (index.html must be at the root - it is).
  4. Deploy, then copy the Slate URL.

Deploy with the CLI instead
  1. Unzip into a folder, cd into it.
  2. catalyst login
  3. catalyst init slate        (pick Basic Web / Static)
  4. catalyst deploy slate --production

Backend note
  The forecasting dashboard, charts and dispatch logic run fully in the browser.
  The Pulse Assistant chat, the AI status check and live weather call a backend
  function at /server/grid_api (endpoints: /chat, /status, /weather).
  If that Catalyst function (grid_api) is not deployed, those three features
  show as offline and everything else still works.
  If the function lives on a different domain, add this line just above the
  closing </head> tag in index.html:
    <script>window.GRID_API_BASE = "https://YOUR-FUNCTION-URL";</script>
