# tp-foaf

Master 2 coursework (La Rochelle University) on the Semantic Web: a personal homepage described with RDF and the FOAF vocabulary, published on GitHub Pages.

- Page: https://fchapoulliep.github.io/tp-foaf/
- FOAF profile: https://fchapoulliep.github.io/tp-foaf/foaf.rdf

## The FOAF profile

`foaf.rdf` (RDF/XML) describes a single `foaf:Person`, identified by `https://fchapoulliep.github.io/tp-foaf/#me`:

- name, given name, family name and nickname (`fchapoulliep`);
- email address (`foaf:mbox`) and title (computer science student);
- homepage and weblog, both pointing to this page;
- a GitHub account (`foaf:OnlineAccount`);
- interests: the W3C RDF and Semantic Web pages;
- a Dublin Core description (`dc:description`).

## How the page uses it

`index.html` is a plain static page that links to the profile and repeats part of it as RDFa:

- `<link rel="alternate" type="application/rdf+xml">` and `<link rel="meta">` point to `foaf.rdf`, so RDF tools can discover the profile from the page.
- The profile section uses the same subject (`about="...#me"`, `typeof="foaf:Person"`) and marks the heading as `foaf:name`, the GitHub link as `foaf:homepage` and the email link as `foaf:mbox`.

## Report

`compteRendu.pdf` is the lab report, in French. It covers four exercises:

1. Writing `foaf.rdf`, linking it to the homepage with RDFa and deploying on GitHub Pages, then checking it with the W3C RDF validator.
2. Exporting an ORCID profile as Turtle with `curl`.
3. Creating a Solid profile on solidweb.org. The Media Kraken movie list could not be done because the app was unavailable.
4. Crawling from the page with LDSpider to discover other FOAF profiles (2,692 triples parsed).

## Run locally

There is no build step: open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server
```

GitHub Pages serves the root of the `main` branch.

## Files

| File | Content |
| --- | --- |
| `index.html` | Homepage with RDFa annotations |
| `index.css` | Page styles |
| `foaf.rdf` | FOAF profile in RDF/XML |
| `compteRendu.pdf` | Lab report (French) |
