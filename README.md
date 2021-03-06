# gVisor Website

This repository holds the content for the gVisor website. It uses
[hugo](https://gohugo.io/) to generate the website and
[Docsy](https://github.com/google/docsy) as the theme. 

## Requirements

Building the website requires the extended version of
[hugo](https://gohugo.io/) and [node.js](https://nodejs.org/) in order to
generate CSS files. Please install them before building.

- Node.js >= 10.15.0 LTS
- hugo extended >= v0.53

## Contributing to Documentation

### Using Github

You can use the "Edit this page" link on any documentation page to edit the
page content directly via GitHub and submit a pull request. This should
generally be done for relatively small changes.

### Using Git

You can submit pull requests by making changes in a Git branch. See more
information on GitHub pull requests
[here](https://help.github.com/en/articles/about-pull-requests).

Documentation is located in the [content/docs/](content/docs/) directory.
Documentation is written in markdown with hugo extensions. Please read more
about [content management](https://gohugo.io/categories/content-management) in
the hugo documentation.

You can use the hugo web server for testing. This will start a webserver that
will rebuild the site when you make content changes:

```
make server
```

Access the site at http://localhost:8080

## Building

If you are making changes to App Engine config or application code, you can
build the website using `make`. This will output the App Engine application
code, configuration, and html and CSS into the `public/` directory.

```
make
```

If you have Go installed you can run a local version of the website via the
`public/` directory.

```
cd public/
go run main.go
```

Access the site at http://localhost:8080

## Troubleshooting

#### I get errors when building the website.

If you get the following errors you should check that you have the "extended"
version of Hugo. This is the version of hugo named "hugo\_extended" on the
[releases page](https://github.com/gohugoio/hugo/releases).

```
ERROR 2019/04/03 11:25:58 Failed to add template "partials/navbar.html" in path "/home/me/gvisor-website/layouts/partials/navbar.html": template: partials/navbar.html:5: function "resources" not defined
ERROR 2019/04/03 11:25:58 partials/navbar.html : template: partials/navbar.html:5: function "resources" not defined
ERROR 2019/04/03 11:25:58 Unable to locate template for shortcode "readfile" in page "docs/user_guide/docker.md"
ERROR 2019/04/03 11:25:58 Unable to locate template for shortcode "readfile" in page "docs/user_guide/oci.md"
ERROR 2019/04/03 11:25:58 Unable to locate template for shortcode "blocks" in page "_index.html"
```
