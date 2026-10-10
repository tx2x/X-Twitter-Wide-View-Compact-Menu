# X (Twitter) Wide View + Compact Menu

A pure-CSS [Stylus](https://add0n.com/stylus.html) userstyle for **x.com / twitter.com** that gives you a cleaner, roomier layout: no right sidebar, a full-width timeline, a compact left menu, and fine-grained control over what stays visible.

No JavaScript. No permissions. No network requests. Every feature is an option you can toggle from the Stylus popup.

---

## Features

- **Wide view** — removes the right column (search, "What's happening", "Who to follow") and stretches the timeline to the full window width on Home, post pages, search, profiles and all profile tabs (Posts, Replies, Media, ...).
- **Compact left menu** — reduces the vertical spacing between menu items. The amount is adjustable with a slider (0–16 px).
- **Hide any menu item** — X logo, Home, Explore, Notifications, Messages, Grok, Calls, Creator Studio, Jobs, Communities, Premium, Verified Orgs, Profile, More, the Post button and the account switcher. Nothing is hidden by default.
- **Hide floating buttons** — remove the Chat and Grok buttons in the bottom-right corner.
- **Interface opacity** — fade the whole left menu with a single slider, optionally together with the top bar (section title, back button, tabs). Full opacity can be restored on hover. Posts are never affected.
- **Softer separators** — one slider controls the opacity of all separator lines at once: the horizontal lines between posts, the line under profile tabs, and the vertical lines on both sides of the post area. Set it to 50% for subtle lines or 0% to hide them completely.
- **Theme aware** — separators adapt to the Default (light), Dim and Lights out themes.
- **Language independent** — selectors rely on stable `data-testid` / `href` values rather than interface text, so it works with any interface language.

## Screenshots

<!-- SCREENSHOT: the Stylus options panel with all the settings visible -->
![Stylus options panel](https://github.com/tx2x/X-Twitter-Wide-View-Compact-Menu/blob/main/stylus-options-screenshot.png?raw=true)

## Options

Click the Stylus icon while on x.com, find the style in the list and open its options (or open the style from the Stylus manager). The options are generated from the header of the file.

### Layout

| Option | Default | Description |
|---|:---:|---|
| Wide view | On | Removes the right column and stretches the timeline to full width. |
| Compact left menu | On | Reduces the spacing between left-menu items. |
| Compact menu: vertical padding | 4 px | Padding of each menu item (0–16 px). Lower is more compact. |

### Opacity

| Option | Default | Description |
|---|:---:|---|
| Left menu opacity | 1 | Opacity of the whole left menu (0.1–1). `1` means no change. |
| Restore full opacity on hover | On | The menu (and top bar) becomes fully opaque while hovered. |
| Apply the same opacity to the top bar | On | Also fades the section title, back button and tabs. |
| Separator lines opacity | 100 | `100` = normal, `50` = half as visible, `0` = hidden. Affects horizontal and vertical separators. |

### Hide floating buttons

| Option | Default |
|---|:---:|
| Chat (bottom right) | Off |
| Grok (bottom right) | Off |

### Hide menu items

All options are **off by default**.

| | | | |
|---|---|---|---|
| X logo | Home | Explore | Notifications |
| Messages | Grok | Calls | Creator Studio |
| Jobs | Communities | Premium | Verified Orgs |
| Profile | More | Post button | Account switcher |

## Compatibility

- **Browsers:** Chromium-based browsers 111+ (Chrome, Edge, Brave, Opera, Vivaldi) and Firefox 121+, with the Stylus extension.
- **Sites:** `x.com` and `twitter.com`.
- **Themes:** Default (light), Dim and Lights out.

The style uses modern CSS (`:has()`, `color-mix()`), which is why older browsers are not supported.

## How it works

The file is a [UserCSS](https://github.com/openstyles/stylus/wiki/Usercss) style written with the Stylus preprocessor. The options in the header are compiled by Stylus, so **disabled features add no CSS at all**. Selectors are anchored at a few well-known elements and use child combinators of limited depth, which keeps matching cheap. All rules that hide elements are merged into a single rule.

Opacity settings only touch the menu, the top bar and border colors. They never change the opacity of post content (text, images, video).

## Known limitations

- The style depends on the markup of X. When X changes its layout, some selectors may need to be updated.
- The selectors for **Calls** are best-effort, because the exact markup of this item is not documented. If it does not disappear, please open an issue.
- Separator colors are derived from the theme's text color, so at 100% they are untouched and at other values they are a close approximation of the original line color.

## Troubleshooting / reporting issues

If something does not work, please open an issue and include:

1. The page where it happens (Home, profile, post, search, ...) and your theme (Default / Dim / Lights out).
2. The HTML of the element: right-click it → **Inspect** → right-click the highlighted node → **Copy** → **Copy outerHTML**.
3. Your browser and version.

## Credits

Inspired by the [Twitter Wide View](https://chromewebstore.google.com/detail/twitter-wide-view/ibokdibmagcemmllgdhapnmnlebchlae) browser extension, reimplemented as a pure-CSS userstyle with many additional options. Thanks to the authors of public X userstyles whose work helped in researching the page structure.
The code was written using Claude Sonnet 5.5.

## License

[MIT](LICENSE)
