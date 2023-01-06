Install Docker Desktop
Recommended approach to install Docker Desktop on Ubuntu:

Set up Docker’s package repository.

Download latest DEB package.

Install the package with apt as follows:


 sudo apt-get update
 sudo apt-get install ./docker-desktop-<version>-<arch>.deb
Note

At the end of the installation process, apt displays an error due to installing a downloaded package. You can ignore this error message.


N: Download is performed unsandboxed as root, as file '/home/user/Downloads/docker-desktop.deb' couldn't be accessed by user '_apt'. - pkgAcquire::Run (13: Permission denied)
There are a few post-install configuration steps done through the post-install script contained in the deb package.

The post-install script:

Sets the capability on the Docker Desktop binary to map privileged ports and set resource limits.
Adds a DNS name for Kubernetes to /etc/hosts.
Creates a link from /usr/bin/docker to /usr/local/bin/com.docker.cli.
Launch Docker Desktop
To start Docker Desktop for Linux, search Docker Desktop on the Applications menu and open it. This launches the Docker menu icon and opens the Docker Dashboard, reporting the status of Docker Desktop.

Alternatively, open a terminal and run:
jgj

 systemctl --user start docker-desktop
When Docker Desktop starts, it creates a dedicated context that the Docker CLI can use as a target and sets it as the current context in use. This is to avoid a clash with a local Docker Engine that may be running on the Linux host and using the default context. On shutdown, Docker Desktop resets the current context to the previous one.

The Docker Desktop installer updates Docker Compose and the Docker CLI binaries on the host. It installs Docker Compose V2 and gives users the choice to link it as docker-compose from the Settings panel. Docker Desktop installs the new Docker CLI binary that includes cloud-integration capabilities in /usr/local/bin and creates a symlink to the classic Docker CLI at /usr/local/bin/com.docker.cli.

After you’ve successfully installed Docker Desktop, you can check the versions of these binaries by running the following commands:


 docker compose version
 docker --version
 docker version
To enable Docker Desktop to start on login, from the Docker menu, select Settings > General > Start Docker Desktop when you log in.

Alternatively, open a terminal and run:


 systemctl --user enable docker-desktop
To stop Docker Desktop, select the Docker menu icon to open the Docker menu and select Quit Docker Desktop.

Alternatively, open a terminal and run:


 systemctl --user stop docker-desktop
Upgrade Docker Desktop🔗
Once a new version for Docker Desktop is released, the Docker UI shows a notification. You need to download the new package each time you want to upgrade Docker Desktop and run:
