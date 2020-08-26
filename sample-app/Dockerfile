FROM nginx:1.19.2-alpine-perl as base
COPY index.html /usr/share/nginx/html/index.html
COPY entrypoint env-subst /bin/
ENTRYPOINT [ "sh", "/bin/entrypoint" ]

FROM base as v1
ENV background=white text="Version 1"
RUN sh /bin/env-subst /usr/share/nginx/html/index.html

FROM base as v2
ENV background=white text="Version 2"
RUN sh /bin/env-subst /usr/share/nginx/html/index.html

FROM base as blue
ENV background="#4169E1" text="Blue Version"
RUN sh /bin/env-subst /usr/share/nginx/html/index.html

FROM base as green
ENV background="#8dc63f" text="Green Version"
RUN sh /bin/env-subst /usr/share/nginx/html/index.html

