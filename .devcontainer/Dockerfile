FROM alpine

ARG USERNAME=devuser
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
# デフォルトだとコンテナ内のユーザがrootになってしまうので、ホスト側1000が存在することを前提にユーザを作る
RUN apk update && \
    apk add --no-cache bash && \
    addgroup -g $USER_GID $USERNAME && \
    adduser -u $USER_UID -G $USERNAME -s /bin/bash -D $USERNAME

USER $USERNAME
WORKDIR /home/$USERNAME