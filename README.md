# Rack

A gym logging app that runs in the browser and stores everything on the person's own phone. No accounts, no server.

## Files

```
index.html      the app people use in the gym
builder.html    the coach's page for building plans
plans/          one JSON file per person, e.g. plans/hugo.json
icon.png        optional, 180×180 – the home-screen icon
```

## Hosting

Upload the whole folder to any static host (GitHub Pages, Netlify, Cloudflare Pages, or a plain web server). No build step.

## Giving someone a plan

1. Open `builder.html`. Either build the sessions by hand, or click **Import from workbook** and pick the client's coaching sheet downloaded as Excel (in Google Sheets: File → Download → Microsoft Excel). It reads the client's name, the Training Plan sessions (order, sets, rep range) and the video links from the Exercise Log. Check it over and adjust anything.
2. Either
   - **Download plan file** → upload it into `plans/` → send the person `index.html?plan=<id>`, or
   - **Copy share link** → text them the link (the plan is inside the link, no upload needed).
3. They open the link in Safari, tap Share → Add to Home Screen. From then on it works offline.

## Updating a plan

Open the old file in the builder (it bumps the version for you), make changes, download, replace the file in `plans/`. Next time the person opens the app online it offers to apply the update. Their history is untouched.

## Notes

- Data lives in Safari's storage on that phone only. The app has Export/Restore backup under Exercises → Your data.
- `plans/hugo.json` is Hugo's current plan from the workbook; open `index.html?plan=hugo` to load it.
