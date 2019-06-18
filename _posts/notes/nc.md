commands:
    nc -lp 3333 -c bash(cmd)
    nc -nv 1.1.1.1 3333
dirs:
    tar cfz - * | nc 192.168.10.1 3333
    nc -lv 3333 | tar xfvz - 

tar -cvf - music/ | nc -lp 3333 -q 1

nc -nv 1.1.1.1 3333 | tar -xvf -

crypt:(or using cryptcat)
    nc -lp 3333 | mcrypt --flush -Fbqd -a rijndael-256 -m ecb > 1.mp4
    mcrypt --flush -Fbq -a rijndael-256 -m ecb < a.mp4 | nc -nv 1.1.1.1 3333 -q 1
clone disks:
    nc -lp 3333 | dd of=/dev/sda
    dd if=/dev/sda | nc -nv 1.1.1.1 3333 -q 1

ncat -l 192.168.10.1 4444 -v --allow 192.168.10.5 -c cmd.exe --keep-open

