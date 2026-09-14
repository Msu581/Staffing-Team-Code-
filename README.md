# CoE Verification Suite

Three previously separate projects merged into one repository.

## Structure

    index.html                        Sign-in portal
    script.js  style.css  season.*    Portal assets
    assets/logo.png
    apps/allinone/index.html          Gradesheet Verification Tool
    apps/white-vs-original/index.html Grade Sheet Verification Toolkit

## Running locally

No build step and no dependencies. Serve the folder over HTTP:

    python3 -m http.server 8000

Then open http://localhost:8000

Opening index.html with a file:// path is not recommended — some
browsers restrict the CDN scripts the tools rely on.

## Deploying

Push to GitHub, then Settings -> Pages -> Deploy from branch -> main / (root).
Everything lives at one URL, e.g. https://<user>.github.io/<repo>/

## Editing the tools

apps/allinone/index.html and apps/white-vs-original/index.html are
byte-for-byte copies of the originals. Each is a single self-contained
HTML file. Replace the whole file to update a tool.

## Sign-in

The sign-in list is the CREDENTIALS block near the top of script.js.
This is a convenience gate, not security: GitHub Pages serves every
file publicly, so anyone who types /apps/allinone/ directly reaches the
tool without signing in. Do not put confidential data in these tools.
