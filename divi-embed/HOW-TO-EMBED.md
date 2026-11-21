# Embedding the Larkline prototype on aithal.me (Divi 5)

Each page is one paste-ready snippet for a Divi Code module:

- `larkline-home-divi.html` → the home page
- `larkline-property-divi.html` → the Orange Avenue Ranch property page

The prototype is drawn inside a Shadow DOM, so your Divi styles and the prototype's styles can't affect each other.

## 1. Upload the office photo
Media → Add New → upload `Prototype v1/assets/office.jpg`. Copy its File URL.

## 2. Create two pages
- **Larkline**, slug `larkline` → URL `/larkline/`
- **Orange Avenue Ranch**, slug `orange-avenue-ranch`, parent **Larkline** → URL `/larkline/orange-avenue-ranch/`

On both pages, hide your site header and footer, because the prototype has its own. Either set the page template to **Blank Page**, or in Theme Builder assign a template with no header or footer to these two pages.

## 3. Add the Code module
On each page: one Section → one Row → one Code module.

- Section: padding 0 on all sides.
- Row: width 100%, max width 100%, padding 0, column gutters off.
- Paste the whole contents of the matching snippet file into the Code module, then save.

## 4. Check the three settings at the top of each script
```
var HOME = "/larkline/";
var PROPERTY = "/larkline/orange-avenue-ranch/";
var OFFICE = "/wp-content/uploads/2026/11/office.jpg";
```
Change `OFFICE` to the URL you copied in step 1. Change `HOME` and `PROPERTY` only if you used different slugs.

## Good to know
- If Divi's visual builder shows a blank Code module, that's normal. The prototype draws when the page loads, so check it in View Page.
- If an animation or caching plugin combines or delays JavaScript (SiteGround Speed Optimizer, WP Rocket), exclude these two pages from JS deferral if the prototype doesn't appear.
- If the mobile menu opens in the wrong place, a Divi section around it probably has a transform or an animation set. Remove the animation on that section.
- The "Our streets" panels pin with `position: sticky`. If they scroll away instead of pinning, a Divi section, row or column around the Code module has overflow set to hidden. Set overflow back to default (visible) on that section, row and column.
- The valuation form is a front-end demo only; it doesn't send anything yet.
