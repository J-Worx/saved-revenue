# Solar Revenue Recovery Calculator

A single-page calculator that shows solar companies how much revenue an automated
customer follow-up workflow can add by recovering deals that fall off before install.

## Inputs (sliders)

1. **Average cost of a solar build** ($5k–$80k)
2. **Units sold per month** (1–300)
3. **% that fall off before install** (0–60%)

## How it calculates

```
fall-off units      = units sold × fall-off %
recovered units     = fall-off units × 65%      (follow-up workflow recovery rate)
total installed     = (units sold − fall-off units) + recovered units
total installed rev = total installed × avg build cost
commission paid     = total installed rev × 3%
revenue added       = recovered units × avg build cost   ← headline number
```

To change the recovery rate or commission rate, edit the constants at the top of the
`<script>` in `index.html`:

```js
const RECOVERY_RATE   = 0.65; // 65% of fall-off deals recovered
const COMMISSION_RATE = 0.03; // 3% of all installed revenue
```

## Publish on GitHub Pages

1. Create a new repository and add `index.html` (and this `README.md`).
2. Push to GitHub.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to `Deploy from a branch`, pick the
   `main` branch and `/ (root)` folder, then **Save**.
5. Your calculator will be live at `https://<your-username>.github.io/<repo-name>/`.

No build step, frameworks, or dependencies — it's one static HTML file.
