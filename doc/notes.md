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


   This was observed post-hoc: GTKTerm has a hexadecimal mode that
   comes in very handy for such situations.  Instead of relying on
   settings and 'programming' ("I thought I had this set the other way!")
   GTKTerm lets you see what your target board's serial io  is *doing*
   even if you don't have any source code for it, to compare to, nor
   any specs.

   It's objective information.

   There is a utility to this: lines that are printed with 0x0a line endings,
   uniquely, do not overwrite one another.  The messages are 'stair-stepped'
   but 100% of the messages are seen (if line-wrapping is functioning, and
   in some other contexts as well).

   Whereas, with 0x0d (singleton) line endings, each line printed overwrites
   the line that came before it, and nothing advances vertically at all.

   For debugging, the former is vastly preferred, one may agree. ;)

end.
