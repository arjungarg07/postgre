## How to kill a process on a port on ubuntu

You want to use backtick not regular tick:

`sudo kill -9 `sudo lsof -t -i:9001` `

If that doesn't work you could also use $() for command interpolation:

`sudo kill -9 $(sudo lsof -t -i:9001)`