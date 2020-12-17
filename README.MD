docker run -it --rm -v $PWD/traefik.toml:/etc/traefik/traefik.toml -v $PWD/dyn:/dyn --network host --name traefik traefik:v2.4
```
Serhii Charykov, [17.12.20 22:52]
127.0.0.1:6379> set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`google`)"
OK
127.0.0.1:6379> set traefik/http/services/test/loadbalancer/servers/0/url "http://google.com"
OK
127.0.0.1:6379> set traefik/http/routers/test/service test
OK
127.0.0.1:6379> set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google/`)"
OK
127.0.0.1:6379> set traefik/middlewares/test/stripprefix/prefixes/0 "/google"
OK
127.0.0.1:6379> set traefik/middlewares/test/strip-prefix/prefixes/0 "/google"
OK
127.0.0.1:6379> set traefik/middlewares/test/stripPrefix/prefixes/0 "/google"
OK
127.0.0.1:6379> set traefik/middlewares/test1/stripPrefix/prefixes/0 "/google"
OK
127.0.0.1:6379> set traefik/middlewares/test1/stripPrefix/prefixes/0/ "/google"
OK
127.0.0.1:6379> set traefik/middlewares/test1/stripPrefix/prefixes/0 "/google"
OK
127.0.0.1:6379> set traefik/middlewares/test1/stripPrefix/prefixes/0 "google"
OK
127.0.0.1:6379> set traefik/middlewares/test1/stripPrefix/prefixes/0 "/google"
OK
127.0.0.1:6379> set "traefik/middlewares/test1/stripPrefix/prefixes/0" "/google"
OK
127.0.0.1:6379> set "traefik/http/middlewares/test1/stripPrefix/prefixes/0" "/google"
OK
127.0.0.1:6379> set traefik/http/routers/test/middlewares/0 "test"
OK
127.0.0.1:6379> set traefik/http/routers/test/middlewares/0 "test1"
OK
127.0.0.1:6379> set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "false"
OK
127.0.0.1:6379> set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "falses"
OK
127.0.0.1:6379> set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "true"
OK
127.0.0.1:6379> set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google`)"
OK
127.0.0.1:6379> set "traefik/http/middlewares/test1/stripPrefix/forceSlash" "false"
OK
127.0.0.1:6379> set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google1`)" EX 10
OK
127.0.0.1:6379> set traefik/http/routers/test/rule "Host(`localhost`) && PathPrefix(`/google1`)" EX 10
OK
127.0.0.1:6379>
```