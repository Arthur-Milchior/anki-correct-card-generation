# More consistent cards generation
## Rationale
If you are a power user, you may want to be able to use complex
template. The rule «a card is generated if and only if the question
side show the content of a field» is a really nice rule. But that's
far from being what anki actually does. See [generation
ules](https://github.com/Arthur-Milchior/anki/blob/commented/documentation/templates_generation_rules.md)
for a real explanation

So, this add-on change anki, in order to ensure that cards are
generated if only if they should be generated !


## Warning
### Computer only
It should sadly be noted that this add-on is kind of incompatible with
any version of anki without this addon. It means that some cards may
be generated here, and be seen as empty on ankidroid/ankiweb/ios.

### Cloze deletion
This add-on only deals with non-cloze notes. In the case of cloze
note, this add-on use the anki's standard algorithm to decide which
cards remain. This may change in the future

## Internal
It changes the following methods:
* ```Template.render_unescaped```, it now returns a pair, whose second
  element is True if and only if the field was found and
  showAField. (Currently, the field may be a special field. TODO: remove this)
* ```Template.render_tags```: similarly, it returns a pair, which is
  true if only if some field was found and showAField.
* ```Template.render```: same modification
* ```_Collection._renderQA```: The dictionnary returned contains an
  entry "showAField" which has the meaning of the previous change
* ```Card.isEmpty```: it now returns the correct answer !
* ```ModelManager.availOrds```: Same thing

## Version 2.0
None

## Anki > 2.1.19
Anki changed a lot in version 2.1.20. I am currently unable to
understand those change, as they are in rust, and I don't know
it. Furthermore, rules for card generation change, so it's possible
that this add-on becomes useless. Anyway, until I know more about
2.1.20, this add-on won't be available with latest anki. As this
add-on as only peen downloaded 63 times, I believe that's not a real trouble.

## TODO
* Do not consider cards with only special fields as successful cards.
* Also correct cloze deletion generation

## Links, licence and credits

Key         |Value
------------|-------------------------------------------------------------------
Copyright   | Arthur Milchior <arthur@milchior.fr>
Based on    | Anki code by Damien Elmes <anki@ichi2.net>
License     | GNU AGPL, version 3 or later; http://www.gnu.org/licenses/agpl.html
Source in   | https://github.com/Arthur-Milchior/anki-correct-card-generation
Addon number| [1713990897](https://ankiweb.net/shared/info/1713990897)
