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
