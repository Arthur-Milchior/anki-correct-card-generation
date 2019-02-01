# Deprecated
This add-on is deprecated, since it was incorporated in anki's default
code in
(2.1.6)[https://apps.ankiweb.net/docs/changes.html#changes-in-2.1.6]
by this (pull
request)[https://github.com/dae/anki/commit/8e0077335a6f1fc03b8045b41fe916bd9dab912d].

The remaining of the README consider the previous documentation.

# New cards are see according to their position, and not their creation time
## Bug corrected
This add-ons corrects the following bug:

* Create a note N in an empty deck D of type basic (reverse), with
only some back, no front. Only card 2 will be generated.
* Edit the note, add a front. Card 1 will be generated.
* In the main window, try to learn deck D. In anki, currently, you'll
  see Card 2 first. According to the manual (and to my common sens),
  it should be Card 1 first.

## Effect
This add-ons ensures that new cards of a same note are seen according
to their order, and not to their creation date.

Works with both schedulers. Work only where the add-on is installed,
thus won't work on ankidroid, IoS, ankiweb, etc... (I don't know
whether this bug exists there or not).

## Commit
This has been submitted as pull-request
(#262)[https://github.com/dae/anki/pull/262] to Anki's code. Thus it
may hopefully become useless.

## Links, licence and credits

Key         |Value
------------|-------------------------------------------------------------------
Copyright   |Arthur Milchior <arthur@milchior.fr>
Based on    |Anki code by Damien Elmes <anki@ichi2.net>
License     |GNU AGPL, version 3 or later; http://www.gnu.org/licenses/agpl.html
Source in   | https://github.com/Arthur-Milchior/anki-correct-card-generation
Addon number| [1666697962](https://ankiweb.net/shared/info/1666697962)
