FROM python:3.8.0a3-alpine3.9

RUN	apk --update add \
		bash \
		curl \
		ca-certificates \
		git \
		less \
		openssl \
		openssh-client \
		p7zip \
		py-lxml \
		py-pip \		
    	&& apk --update add --virtual \
		build-dependencies \
		libffi-dev \
		openssl-dev \
		build-base \
	&& pip install --upgrade \
		pip \		
	&& pip install \
		ansible>=2.8.0 \		
		docker-py \
		dopy  \
		pywinrm  \
		pyvmomi \
		pysphere \
		dictdiffer \
		jinja2 \
		python-string-utils \
		ruamel.yaml \
		six \
	&& apk del build-dependencies \
	&& rm -rf /var/cache/apk/*

RUN	mkdir -p /etc/ansible \		
	&& echo 'localhost' > /etc/ansible/hosts \			
	&& mkdir -p ~/.ssh && touch ~/.ssh/known_hosts
	
ENV PATH="/:${PATH}"

ONBUILD	WORKDIR	/tmp
ONBUILD	COPY 	. /tmp
ONBUILD	RUN	ansible -c local -m setup all > /dev/null
CMD ["bash"]


