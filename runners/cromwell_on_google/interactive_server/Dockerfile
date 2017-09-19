# Copyright 2017 Google Inc.
#
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file or at
# https://developers.google.com/open-source/licenses/bsd

FROM java:openjdk-8-jre

# Copy Cromwell and the Cromwell conf template
RUN mkdir /cromwell
RUN cd /cromwell && \
    curl -L -O https://github.com/broadinstitute/cromwell/releases/download/29/cromwell-29.jar
RUN ln /cromwell/cromwell-29.jar /cromwell/cromwell.jar
COPY jes_template.conf /cromwell/

# Set up the runtime environment
ENV CROMWELL /cromwell/cromwell.jar
ENV CROMWELL_CONF /cromwell/jes_template.conf

WORKDIR /cromwell

# Cromwell's HTTP Port
EXPOSE 8000
