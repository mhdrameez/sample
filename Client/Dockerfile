#
# Dockerfile for a jmeter client.
# A container from this image will be ready to run a jmeter client.
# 
# Usage:
#  docker run -d \
#             -v <absolute path on host>:/logs \
#             -v <absolute path on host>:/input-data \
#             -v <absolute path on host>:/scripts \
#             <docker image> -n \
#                            -LDEBUG # <-- ok, this is optional.
#                            -t /scripts/<script file name> 
#                            -l /logs/<output jtl file name>
#                            -R<server IP addresses>
#


# Use jmeter-base as the foundation
FROM mhdrameez/samples

MAINTAINER mhdrameez

# Create mount point for script, data and log files
VOLUME ["/scripts"]
VOLUME ["/input_data"]
VOLUME ["/logs"]

# Use a predefined configuration.  This sets the contract for connecting to jmeter servers.
ADD jmeter.properties /var/lib/apache-jmeter-$JMETER_VERSION/bin/

ENTRYPOINT [ "/var/lib/apache-jmeter-5.3/bin/jmeter" ]