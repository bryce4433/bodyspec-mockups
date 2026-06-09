# Mochi × BodySpec — integration mockups

Static HTML/CSS design mockups for a proposed integration that lets Mochi patients
book and purchase clinical-grade **BodySpec DEXA** body-composition scans inside the
portal, with results syncing back automatically for the care team to review.

These are **design mockups for internal stakeholder review**, not production code.
BodySpec data and the "sync" are stubbed. There are no API calls or backend.

## View it

Open `index.html` in any browser, or serve the folder:

```bash
python3 -m http.server 8099
# then open http://localhost:8099
```

## What's here

| View                                                  | File                     |
| ----------------------------------------------------- | ------------------------ |
| Hub / index                                           | `index.html`             |
| **Patient** — dashboard entry point                   | `patient/dashboard.html` |
| **Patient** — booking & checkout                      | `patient/booking.html`   |
| **Patient** — upcoming scan / what to expect          | `patient/upcoming.html`  |
| **Patient** — results dashboard (trends + comparison) | `patient/results.html`   |
| **Patient** — scan history                            | `patient/history.html`   |
| **Provider** — patient chart · Body Composition tab   | `provider/chart.html`    |
| Shared tokens + components                            | `assets/mochi.css`       |

## Design system

Built with the real Mochi design tokens pulled from the `mochi-turbo` codebase
(`packages/design-tokens` + `packages/tailwind-config`):

- **Fonts:** Instrument Sans (sans) + STIX Two Text (serif accent)
- **Brand:** navy `#000045`, secondary purple `#3b3b8d`, page background `#f3f6f9`
- **Status:** success `#17b26a`, warning `#f79009`, error `#ea4135`
- **Radius:** 16px cards (patient) / 12px (provider), full-pill buttons, 8px provider buttons
- **Spacing:** 8px scale · soft shadows · Radix-style pill tabs

The patient results dashboard recreates BodySpec's metric-card + percentile-bar layout;
the provider chart recreates an InBody-style cumulative clinical table. Both are
re-rendered in Mochi's visual language rather than embedded as images.

## Sample data

One GLP-1 patient ("Sarah Mitchell", 42, on tirzepatide) with 3 DEXA scans over ~6 months:
~30 lbs lost, 86% of it fat, lean mass largely preserved. The provider view demonstrates
lean-mass flagging (a "Monitor" flag in the first interval that resolves in the second).
