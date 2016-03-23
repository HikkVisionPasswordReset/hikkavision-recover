#hikkavision-recover — IP cameras password recovery tool on Hikvision SDK.

---

## Building

Install Kali Linux

Install Go Language
Install Go Language Color Addon
Setup Go Language
Install MinGw for Windows buildings
Download hikkavision-recover and extract to Home directory

---------------------------------------------------

# apt-get install golang
# mkdir ~/workspace
# echo 'export GOPATH="$HOME/workspace"' >> ~/.bashrc
# source ~/.bashrc
# go get github.com/fatih/color
# apt-get install mingw-w64
# cd ~/hikkavision-recover-master
# make

---------------------------------------------------

I'm using a makefile, so you should be able to build it under Linux using this command:

    # make linux


You can also build it for Windows if you have a MinGW installed:

    # make windows

    
And you can make binaries for Linux and Windows by omiting a make target (it is useful for me as I distribute every build to people who don't know anything about compilers):

    # make


And now you have a `build` directory with compiled app.

---

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
