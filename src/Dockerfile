FROM lscr.io/linuxserver/webtop:ubuntu-kde
LABEL maintainer="Ben Siebert"

# Set environment variables
ENV CUSTOM_USER=user
ENV TITLE="CodeUp Workspace"


# Update & install packages

RUN apt-get update && apt-get install -y \
    wget \
    curl \
    git \
    nano \
    vim \
    htop \
    tmux \
    neofetch \
    && apt-get clean

## Languages
RUN apt-get install openjdk-17-jdk openjdk-17-jre -y
RUN apt-get install python3 python3-pip python3-venv -y

## Programs & Tools
RUN apt-get install firefox -y

# Customization


RUN mkdir -p /usr/share/wallpapers
RUN wget https://codeup.space/_static/images/software-developer-6521720_1920.jpg -O /usr/share/wallpapers/1.jpg

COPY initcw.sh /initcw.sh

RUN echo "bash /initcw.sh" >> /init

# Ports
EXPOSE 3000
