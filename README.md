# Learning how to build a site with hugo

Playing around with instructions I found on [github][bway_usage].

## Initialising a new site

Within the directory you want to work in, run:

    hugo new site sitename

Then start work inside sitename/.

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
