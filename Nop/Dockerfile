FROM  mcr.microsoft.com/dotnet/sdk:7.0
LABEL Author="pk" Organization="ssg chary"
ARG DOWNLOAD_URL=https://github.com/nopSolutions/nopCommerce/releases/download/release-4.60.3/nopCommerce_4.60.3_NoSource_linux_x64.zip
ARG HOME_DIR=/nopCommerce
ARG user=nop
ARG group=nop
ARG uid=1000
ARG gid=1000
RUN apt update && apt install unzip -y
# Create group nopCommerce
RUN groupadd -g ${gid} ${group} \
    && useradd -d "$HOME_DIR" -u ${uid} -g ${gid} -m -s /bin/bash ${user}
USER ${user}
WORKDIR ${HOME_DIR}
ADD --chown=${user}:${group} ${DOWNLOAD_URL} ${HOME_DIR}/nopCommerce_4.60.3_NoSource_linux_x64.zip
RUN unzip ${HOME_DIR}/nopCommerce_4.60.3_NoSource_linux_x64.zip && \
    mkdir ${HOME_DIR}/bin && mkdir ${HOME_DIR}/logs
EXPOSE 5000
ENV  ASPNETCORE_URLS="http://0.0.0.0:5000"
CMD [ "dotnet", "Nop.Web.dll" ]