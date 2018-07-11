FROM  ubuntu:latest

RUN apt-get update -q && \
	DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends \
	curl \
	openssh-server \
	ca-certificates && \
	curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash && \
	apt-get install -yq --no-install-recommends gitlab-ce
	     
EXPOSE 22 80 443

ENTRYPOINT ["gitlab-ctl","reconfigure"]
