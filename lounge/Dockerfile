FROM centos:7

RUN yum install -y epel-release && \
    yum install -y nodejs npm && \
    yum clean all

ENV LOUNGE_VERSION v2.3.0-rc.2
ENV NODE_ENV production

RUN npm install -g thelounge@${LOUNGE_VERSION} && \
    npm cache clean

ENV PORT 9000
EXPOSE ${PORT}



ENV LOUNGE_HOME "/home/lounge/data"
RUN mkdir -p "${LOUNGE_HOME}"
# so it can be run as any user
RUN chmod 777 ${LOUNGE_HOME}

VOLUME "${LOUNGE_HOME}"

ENTRYPOINT ["lounge"]
