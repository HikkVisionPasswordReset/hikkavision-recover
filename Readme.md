#hikkavision-recover — IP cameras password recovery tool via Hikvision SDK for <a href="http://goo.gl/lBzgJf">IP Cameras</a>

---

## Building
<br>
Install Kali Linux
<br>
Install Go Language
<br>
Install Go Language Color Addon
<br>
Setup Go Language
<br>
Install MinGw for Windows buildings
<br>
Download hikkavision-recover source and extract to Home directory

---------------------------------------------------
<br>
apt-get install golang
<br>
mkdir ~/workspace
<br>
echo 'export GOPATH="$HOME/workspace"' >> ~/.bashrc
<br>
source ~/.bashrc
<br>
go get github.com/fatih/color
<br>
apt-get install mingw-w64
<br>
cd ~/hikkavision-recover-master
<br>
make

And now you have a `build` directory with compiled app for Windows and Linux

## Usage

You can define some options:

* __-logins, -passwords__ — files where your logins and passwords are stored; it looks for «logins» and «passwords» by default;
* __-check__ — very useful, but still experimental option which allows to check a host before trying to log in (I did some reverse-engineering and I'm not really sure if everything is OK);
* __-shoots__ — a directory where pictures from cameras will be stored; it doesn't download pictures by default;
* __-threads__ — there's no multithreading until you define in how many threads you want to do a job;
* __-csv__ — write results to CSV file.

__Please note that it is hardcoded to read IPs from file called “hosts”!__

A typical cammand is:

hikkavision-recover -threads 200 -check -shoots pics/
