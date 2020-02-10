# Technology Tips

1. How to find lines matching a pattern and delete them?
sed -i '/^HERE IT IS/d' <file>
WARNING: Its better to take a backup when using -i switch of sed:
sed -i.bak '/^HERE IT IS/d' <file>

How to find a line 'not-matching' a pattern and delete them
sed -i '/^HERE IT IS/!d' <file>
WARNING: Its better to take a backup when using -i switch of sed:
sed -i.bak '/^HERE IT IS/!d' <file>

Delete first line for all files.
sed -i '1d' *
Delete last (any) character from all line in all files.
sed -i 's/.$//' *
Delete last ': from all line in all files.
sed -i 's/:$//' *


VIM:
http://vim.wikia.com/wiki/Highlight_unwanted_spaces

" Show all tabs:
/\t

" Show trailing whitespace:
/\s\+$

" Show trailing whitespace only after some text (ignores blank lines):
/\S\zs\s\+$

" Show spaces before a tab:
/ \+\ze\t


Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
0.0.0.0         10.144.15.100   128.0.0.0       UG    1      0        0 ppp0
0.0.0.0         192.168.1.1     0.0.0.0         UG    0      0        0 eth0

That's a route to 0.0.0.0/1 (NOT a default route, a default route is 0.0.0.0/0) pointing to 10.144.15.100 which uses ppp0, plus a default route pointing to 192.168.1.1 which goes out eth0

ip route del 0.0.0.0/1 via 10.144.15.100
ip route del default via 192.168.1.1
