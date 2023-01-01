FROM ruby:2.7-alpine3.15

RUN apk update
RUN apk --no-cache add \
    # development packages
    ruby-dev \
    musl \
    gcc \
    cmake \
    git \
    make \
    curl \
    build-base \
    libc-dev \
    libffi-dev \
    zlib-dev \
    libxml2-dev \
    libgcrypt-dev \
    libxslt-dev \
    #python \
    # pushing to git via ssh
    openssh \
    # permissions to install packages
    sudo \
    # tab completion inside the container
    git-bash-completion

# # https://talk.jekyllrb.com/t/load-error-cannot-load-such-file-webrick/5417/2
RUN gem update --system
RUN gem install bundler -v 2.3.20
RUN gem install jekyll

## Set up user so that we can share ssh credentials.
# see: https://stackoverflow.com/questions/27701930/how-to-add-users-to-docker-container 
ENV USERNAME=jekyll
RUN adduser -D $USERNAME
RUN echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME\
    && chmod 0440 /etc/sudoers.d/$USERNAME

COPY Gemfile /home/$USERNAME

WORKDIR /home/$USERNAME
RUN bundle install 

# # Set up git completion.
#RUN echo "source /usr/share/bash-completion/completions/git" >> /home/$USERNAME/.bashrc

# expose the ports for navigation and live reload
EXPOSE 4000
EXPOSE 35729