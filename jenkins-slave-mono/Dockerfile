FROM evarga/jenkins-slave:latest

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF && \
    echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list && \
    apt-get -q update && \
	apt-get install -y \
    curl \
    git \
    mono-devel && \
    mkdir /jenkins && chmod 777 /jenkins

CMD ["/usr/sbin/sshd", "-D"]