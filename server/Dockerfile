FROM svena/nginx-openresty

COPY nginx.conf /nginx.conf
RUN mkdir /lua
COPY json.lua /lua/json.lua
COPY base64urlunescape.lua /lua/base64urlunescape.lua

# Cleanup
RUN rm -rf /var/cache/apk/*

# Export port
EXPOSE 80 443

ENTRYPOINT ["/usr/local/openresty/bin/openresty", "-g", "daemon off;", "-c", "/nginx.conf"]

