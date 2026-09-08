# erdemyilmaz.me

Portfolio and course index for Erdem Yilmaz. Plain HTML and CSS, no build step, no dependencies, no tracking.

## Layout

```
index.html          home: introduction, course list, contact
courses.html        published and planned courses
about.html          biography, method, licence, contact
404.html            not-found page served by GitHub Pages
assets/css/site.css shared stylesheet (same colour tokens as the courses)
CNAME               custom domain for GitHub Pages
robots.txt, sitemap.xml
```

Courses are separate repositories deployed as GitHub Pages project sites. With the custom domain on this user site, a project repository named `dfx` is served at `https://erdemyilmaz.me/dfx/`. Course links on this site use that full URL so they also work when the site is opened from a local file.

## Deploying (GitHub Pages)

1. Create a repository named `<username>.github.io` and push this folder to its default branch.
2. In the repository settings under **Pages**, set the source to that branch and the root folder. The `CNAME` file sets the custom domain; also enter `erdemyilmaz.me` in the custom domain field and turn on **Enforce HTTPS** once the certificate is issued (usually within an hour of DNS propagating).
3. At the registrar (Porkbun), delete the parking records and add:

| Type | Host | Value |
|---|---|---|
| A | (blank, apex) | 185.199.108.153 |
| A | (blank, apex) | 185.199.109.153 |
| A | (blank, apex) | 185.199.110.153 |
| A | (blank, apex) | 185.199.111.153 |
| AAAA | (blank, apex) | 2606:50c0:8000::153 |
| AAAA | (blank, apex) | 2606:50c0:8001::153 |
| AAAA | (blank, apex) | 2606:50c0:8002::153 |
| AAAA | (blank, apex) | 2606:50c0:8003::153 |
| CNAME | www | `<username>.github.io` |

These are GitHub's published Pages addresses; check the GitHub Pages documentation if a deployment check reports otherwise.

4. Push the course repository as `dfx`, enable Pages on it (branch, root). It appears at `https://erdemyilmaz.me/dfx/` with no further DNS work.

## Editing

Each page is self-contained. Keep the header and footer identical across pages. Style rules match the courses: metric units, no long dashes (write "X to Y"), no employer-specific content. Places that need the author's own words are marked `<!-- AUTHOR: ... -->`.

## Licence

Site code MIT. Course content licences are stated on each course.
