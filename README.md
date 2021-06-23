# Linux
Software, solutions for (Ubuntu) Linux

## Processes

- [Kill a process by clicking on its window](https://www.mfitzp.com/tutorials/kill-unresponsive-applications-on-linux/)

## Built-in Unix commands

- [Search for text in all the files within a directory](https://stackoverflow.com/a/15287389/4892892): `grep -rni "your_keyword" *`

## Security

### [Lynis](https://cisofy.com/documentation/lynis/)
   Lynis is an open-source system auditing tool. No installation is required. Get the latest version by cloning it
   ```bash
   git clone https://github.com/CISOfy/lynis
   ```
   All the usage instructions can be accessed through the command line help: `./lynis show help`.
   
   Some commands I find useful:
   
## Docker

### Use Docker as [non-root](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)

```bash
sudo groupadd docker  # create a group
sudo usermod -aG docker $USER  # add the current user to that group
newgrp docker  # activate the changes to the groups
docker run hello-world  # verify that you can run docker commands without sudo
```

Whenever you want to use Docker without root privileges, type `newgrp docker` to the terminal.

### [Kitematic](https://kitematic.com/)

Download and install the [latest release](https://github.com/docker/kitematic/releases).
To use [without root privileges](https://github.com/docker/kitematic/issues/2528#issuecomment-292029858): open a terminal and type
```bash
newgrp docker
kitematic
```

## Audio-video

### ffmpeg

- [Convert all audio files in a directory](https://stackoverflow.com/a/33766147/4892892)
   ```bash
   for i in *.wav; do ffmpeg -i "$i" -acodec mp3 "${i%.*}.mp3"; done
   ```

