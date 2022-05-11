
  
# FROM fluent/fluentd:v1.14-1

# # Use root account to use apk
# USER root

# # below RUN includes plugin as examples elasticsearch is not required
# # you may customize including plugins as you wish
# RUN apk add --no-cache --update --virtual .build-deps \
#         sudo build-base ruby-dev \
#  && sudo gem install fluent-plugin-elasticsearch -v 7.13.3 \
#  && sudo gem sources --clear-all \
#  && apk del .build-deps \
#  && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem


# USER fluent
# fluentd/Dockerfile

FROM fluent/fluentd:v1.14-debian-1
USER root
RUN gem uninstall -I elasticsearch && gem install elasticsearch -v 7.17.0
RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "5.0.3"]
USER fluent