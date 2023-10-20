# Fake UNAME

Modified to emulate x86_64 centos

uname command is often used in scripts to tell which OS is it running on.
Sometimes, when Linux gets updated too ofter, scripts may fail in abrupt
manner, receiving non-expected values from system uname.

So how to use it?

I run build docker system using this command:
```
docker run --rm -it -v /home/yury:/home/pokyuser \
	-v /data/yocto:/data/yocto \
	-v /home/yury/uname:/bin/uname \
	crops/poky:ubuntu-16.04 \
	--workdir=/home/pokyuser
```

As you can see, uname from /home/yury is presented as /bin/uname
in a running Docker instance.

And it actually did trick for me. I hope, you may also find it
useful in such situations.
