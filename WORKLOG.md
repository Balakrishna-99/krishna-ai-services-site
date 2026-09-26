# WORKLOG

`<what I did> -> <the command I ran> -> <what it actually printed>`

1. Read the images folder -> `Get-ChildItem -LiteralPath "images"` -> 26 files, including `logo.jpg`, `logo-dark.jpg`, `profile.jpg`, `working.jpg`, `speaking.jpg`, `shot1.jpg`-`shot6.jpg`.
2. Read real image sizes -> `Add-Type -AssemblyName System.Drawing; ...FromFile...` -> `logo.jpg 415x415`, `logo-dark.jpg 415x415`, `profile.jpg 762x1024`, `working.jpg 896x1200`, `speaking.jpg 1376x768`, `shot1..shot6 1024x1024`.
3. Built the page -> wrote `index.html` and `styles.css` -> files created.
4. Copied the pictures the page uses -> `Copy-Item -LiteralPath "images\logo.jpg",...` -> 8 files in `krishna-ai-services-site\images`.
5. Served the site locally -> `node <temp>\static-server.js "<site>" 8087` -> `ready http://localhost:8087`.
6. Fetched the page and every asset -> `Invoke-WebRequest http://localhost:8087/...` -> `/ 200`, `/styles.css 200`, all 8 images 200.
7. Verified every local reference in the HTML -> regex over page, fetch each -> `local refs OK: 9 / 9`.
8. Verified no price anywhere -> regex over page -> `Rs (case-sensitive): 0`, `35,000 / 35000: 0`, `word price: 0`.
9. Verified contact links -> regex over page -> 4x `https://cal.com/krishna-ai-services/20-min-ai-business-discovery-call-with-balakrishna`, `https://wa.me/919962268122?text=...`, `mailto:bala.krishna47p@gmail.com?subject=...`.
