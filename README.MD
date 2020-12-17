docker run -it --rm -v $PWD/traefik.toml:/etc/traefik/traefik.toml -v $PWD/dyn:/dyn --network host --name traefik traefik:v2.4
```
set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`google`)"
set traefik/http/services/test/loadbalancer/servers/0/url "http://google.com"
set traefik/http/routers/test/service test
set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google/`)"
set traefik/middlewares/test/stripprefix/prefixes/0 "/google"
set traefik/middlewares/test/strip-prefix/prefixes/0 "/google"
set traefik/middlewares/test/stripPrefix/prefixes/0 "/google"
set traefik/middlewares/test1/stripPrefix/prefixes/0 "/google"
set traefik/middlewares/test1/stripPrefix/prefixes/0/ "/google"
set traefik/middlewares/test1/stripPrefix/prefixes/0 "/google"
set traefik/middlewares/test1/stripPrefix/prefixes/0 "google"
set traefik/middlewares/test1/stripPrefix/prefixes/0 "/google"
set "traefik/middlewares/test1/stripPrefix/prefixes/0" "/google"
set "traefik/http/middlewares/test1/stripPrefix/prefixes/0" "/google"
set traefik/http/routers/test/middlewares/0 "test"
set traefik/http/routers/test/middlewares/0 "test1"
set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "false"
set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "falses"
set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "true"
set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google`)"
set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "false"
set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google1`)" EX 10
set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google1`)" EX 10

```