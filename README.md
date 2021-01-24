# Learning how to build a site with hugo

Playing around with instructions I found on [github][bway_usage].

## Initialising a new site

Within the directory you want to work in, run:

    hugo new site sitename

Then start work inside sitename/.

## Ananke theme with Hugo on Elementary OS

Themes are needed for Hugo to present content. To define a theme,
add a line specifying it into your site's `config.toml`:

    theme = "ananke"  # add this line into the file.

Of course, you'll have to include the actual theme, which can be
done via a `git submodule` or unzipping the archive into `themes/`
as in [here][quickstart].

With Elementary OS 5.1.7, Hugo 0.40.1 was provided, which only
works with Ananke v2.51.

+[quickstart]: https://gohugo.io/getting-started/quick-start/

## Editing with preview

Running a live server with drafts on port 3333 while editing:

    hugo server -p 3333 -wDs ./ -d dev/

Remember to make sure the `dev/` directory is not published.

## Serving the live site

Finally, when editing is done, make it live:

    hugo server --baseURL=http://test.site \
                --port=80 \
                --appendPort=false \
                --bind=999.999.999.999  # obviously fake IP

## Adding SSL

In future, I will try to add SSL along [these lines][skarlso_ssl]. This
will require `haproxy` and `certbot` too.

[bway_usage]: https://bwaycer.github.io/hugo_tutorial.hugo/overview/usage
[skarlso_ssl]: https://skarlso.github.io/2017/02/15/how-to-https-with-hugo-letsencrypt-haproxy/
