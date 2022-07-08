Fri  8 Jul 01:38:33 UTC 2022

   The Arduino IDE generated program under testing generates
   both 0x0d and 0x0a line ending chars for each newline.

   The mecrisp-stellaris target, on the other hand, has assembler
   source code organized to send just one of these characters
   (it can be configured for either, but not both, without
   code modifications).

   Currently, the mecrisp target (micro:Bit) has been reconfigured
   for 0x0d line endings, on the notion that this was less
   non-standard. ;)

   It's also the target that currently is supported to about 4800 bps;
   any faster and characters are dropped.

end.
