FROM registry.access.redhat.com/ubi8/ubi-minimal
RUN microdnf update -y && microdnf install -y \
	git zip unzip tar xz && microdnf clean all
RUN microdnf install -y hostname which 
WORKDIR /
ENTRYPOINT [""]