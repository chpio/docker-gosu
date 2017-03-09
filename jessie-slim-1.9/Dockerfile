FROM debian:jessie-slim

RUN { \
	set -ex; \
	VERSION="1.9"; \

	BUILD_DEPS="curl ca-certificates"; \
	apt-get update; \
	apt-get install --no-install-recommends -y $BUILD_DEPS; \

	curl \
		-o /usr/bin/gosu \
		-fsSL \
		"https://github.com/tianon/gosu/releases/download/$VERSION/gosu-$(dpkg --print-architecture)"; \
	chmod +x /usr/bin/gosu; \

	# clean up
	apt-get purge -y $BUILD_DEPS; \
	apt-get autoremove -y; \
	rm -rf /var/lib/apt/lists/*; \
}
