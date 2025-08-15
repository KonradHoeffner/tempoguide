<script>
class Card extends HTMLElement {
    constructor() {super();}

    connectedCallback() {
        const cardName = this.getAttribute('name');
        if (cardName) {
            const encodedCardName = encodeURIComponent(cardName);
            const imageUrl = `https://api.scryfall.com/cards/named?exact=${encodedCardName}&format=image&version=small`;
            // https://github.com/konradhoeffner/mtgindex would give nicer versions but loading timing it is complicated in Markdown
            this.innerHTML = `<img src="${imageUrl}" alt="${cardName}" title="${cardName}">`;
        }
    }
}

class YoutubeVideo extends HTMLElement {
    constructor() {super();}

    connectedCallback() {
        const id = this.getAttribute('id');
        if (id) {
            const t = this.getAttribute('t');
            //let href = "https://www.youtube.com/watch?v="+id;
            //if(t) href+=`&t=${t}s`;
            let embedUrl = "https://www.youtube.com/embed/"+id;
            if(t) embedUrl+=`?start=${t}`;
            this.innerHTML = `<iframe width="560" height="315" src="${embedUrl}" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>`;
        }
    }
}

customElements.define('mtg-card', Card);
customElements.define('youtube-video', YoutubeVideo);
//document.body.style.visibility = 'visible';
</script>

**DRAFT, [CONTRIBUTIONS WELCOME](https://github.com/KonradHoeffner/tempoguide)**

<mtg-card name="Nethergoyf"/>
<mtg-card name="Tamiyo, Inquisitive Student"/>
<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Kaito, Bane of Nightmares"/>
<mtg-card name="Daze"/>
<mtg-card name="Wasteland"/>

## Example List: [MTGO Challenge 2025-07-20](https://www.mtggoldfish.com/deck/7248927#paper)

* 4 Nethergoyf
* 3 Tamiyo, Inquisitive Student
* 4 Orcish Bowmasters
* 2 Murktide Regent
* 2 Brazen Borrower
* 2 Kaito, Bane of Nightmares
* 4 Brainstorm
* 4 Ponder
* 2 Nihil Spellbomb
* 4 Force of Will
* 3 Daze
* 4 Fatal Push
* 3 Thoughtseize
* 2 Bloodstained Mire
* 4 Polluted Delta
* 1 Flooded Strand
* 1 Scalding Tarn
* 4 Underground Sea
* 1 Undercity Sewers
* 1 Island
* 1 Swamp
* 4 Wasteland

* 2 Blue Elemental Blast
* 2 Faerie Macabre
* 2 Force of Negation
* 2 Barrowgoyf
* 2 Harbinger of the Seas
* 2 Consign to Memory
* 1 Null Rod
* 2 Sheoldred’s Edict

## Card Choices

### Mana Base
<mtg-card name="Underground Sea"/>
<mtg-card name="Polluted Delta"/>
<mtg-card name="Flooded Strand"/>
<mtg-card name="Bloodstained Mire"/>
<mtg-card name="Undercity Sewers"/>
<mtg-card name="Island"/>
<mtg-card name="Swamp"/>
<mtg-card name="Wasteland"/>

You don't really have to think about tuning the mana base because it's always the same 19.
You have four Underground Sea, four Polluted Delta, basic Island, basic Swamp, Undercity Sewers.
Then you usually include two blue fetches and two black fetches so you have equal opportunities to fetch both basics.
This is especially important against 8 Moon, also known as Dragon Stompy.
I personally value style and like old border so I play two Flooded Strand and two Bloodstained Mire but there may be some really fringe benefits of splitting them up against Pithing Needle or representing another deck.
And of course you play four Wastelands, especially now that Harbingers don't kill Sagas anymore.
The only possible adaptation is if you have a bigger build, for example with Dauthi Voidwalkers instead of Nethergoyfs, you can add a second Undercity Sewers as a 20th land and go down to two Daze.
The second Sewers also makes you look like Reanimator and if you dont play Goyf, high-level opponents may sideboard incorrectly.

### Core Cards

#### Tempo Shell
<mtg-card name="Force of Will"/>
<mtg-card name="Daze"/>
<mtg-card name="Wasteland"/>
<mtg-card name="Ponder"/>
<mtg-card name="Brainstorm"/>

We are a blue Tempo deck so no surprises here, all four-offs except only three Daze because we are slightly slower then red Tempo and have 19 lands.

#### Creatures
<mtg-card name="Nethergoyf"/>
<mtg-card name="Tamiyo, Inquisitive Student"/>
<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Murktide Regent"/>
<mtg-card name="Barrowgoyf"/>

There is the basic core of Nethergoyfs and Tamiyo's and Orcish Bowmasters.
You play at least three of each but I always play 4 Nethergoyf and 4 Orcish Bowmasters.
Some people play less Nethergoyfs and play more Baleful Strix but here I only cover the variant with at least three Nethergoyfs.
You almost always play one or two Brazen Borrower just as a catch-all answer to stuff like Ensnaring Bridge or Chalice of the Void.
And the name of the game of this deck is consistency so this fits really well, as you want to have an out to a lot of things.

#### Tamiyo, Inquisitive Student

Bowmastering at their end step to draw the Brainstorm out is OK sometimes.
APNAP comes into play: Active players triggers go on stack first.
On their turn if they Brainstorm you play Bowmasters, ping something, they draw 3 triggering Bowmasters 3 times and triggering Tamiyo's flip, resolve brainstorm, flip goes on stack, then your 3 Bowmasters triggers, and hopefully kill their Tamiyo, so probably not a good play, but on our turn these triggers are switched.
This allows you to consider flipping Tamiyo at odd times in the face of a Bowman if you have an answer to their consequent board state.
Often against Bowmasters mirrors, just using your mana efficiently to sorcery speed a clue away from Bowmasters mana is correct.


#### Nethergoyf
<mtg-card name="Nethergoyf"/>
<mtg-card name="Murktide Regent"/>
<mtg-card name="Rest in Peace"/>
<mtg-card name="Rest in Peace"/>

People were initially skeptical but most play 4 now for good reasons.
Large and cheap beater, good blocker, enables Kaito and can even sometimes come back from the grave in grindy matches.
Can grow Murktide Regent for lethal, weak to an anti-graveyard meta (Rest in Peace, Nihil Spellbomb, Leyline of the Void, Dauthi Voidwalker).
Against Izzet try to play at 3/4 or with instant speed growth to 3/4.

#### Murktide Regent vs Barrowgoyf
Murktide Kills faster against combo and control but Barrowgoyf stabilizes extremely well.
Murktide is immune to Fatal Push but dies to Pyroblast.
Barrowgoyfs main can free a sideboard slot but can backfire against UB Reanimator.
Blue count g1 is a consideration here, how many decks in the upper meta is Barrowgoyf good against vs Murktide?
Murktide: Reanimator, Izzet, UB Tempo, Oops, can mention others but those are the main perks.
Barrowgoyf: Red Stompy, Izzet, UB Tempo.

#### Brazen Borrower
<mtg-card name="Brazen Borrower"/>

Can bounce stuff that Fatal Push doesn’t hit, like Murktide Regent, Chalice of the Void, Ensnaring Bridge, Marit Lage, a flipped Tamiyo and much much more.
While bounce is less powerful than removal in a vacuum, UB doesn’t have flexible 2 mana removal spells like Molten Collapse or Witherbloom Command, so this is currently our best option.
Maybe Wizards will print a UB command in the future?
Can also bait an opponent to play Orcish Bowmasters on the 3/1, allowing you to follow up with your own Bowmasters.

#### Fatal Push
<mtg-card name="Fatal Push"/>
Kills most relevant creatures in Legacy, so play 4.

#### Cantrips

Core cantrips, 4 of each are required, but I sometimes board out a Ponder.

#### Kaito, Bane of Nightmares
<mtg-card name="Kaito, Bane of Nightmares"/>

Formerly niche card but since the Frog ban firmly established as a two of value engine that is hard to remove and can disable creatures like Murktide Regent or even Emrakul.
If you are attacking with a creature with power >3 on MTGO, set a stop at the damage step and Ninjutsu Kaito in, you get the damage and the planeswalker, very good with Barrowgoyf and Murktide situationally.
It's important to set a stop in combat because if you play with stops there, your opponent will know you are not Reanimator because you have Kaito in the deck.
Important to consider stun and tick up timing:
If you stun something first you are at 2 loyalty, they lose one stun counter, now if you draw with Kaito you will need to tick up on the next turn in order to stun again if you haven't found an answer.
The board state will determine the right move but important to consider.
Remember you can ninjutsu your Kaito with another Kaito.


### Nihil Spellbomb
<mtg-card name="Nihil Spellbomb"/>

Besides the obvious applications it also grows your own Murktide Regent.
You must consider Spellbombing when the opponent could play Murktide Regent next turn, so pay attention to the number of cards in your opponents graveyard.
Against Reanimator you need a bit more nuance here, can you beat Murktide otherwise?
Do you have FoW?
Can you afford to unlock their graveyard?
Undercity Sewers can help you make hard decisions by informing you of your next draw if it is desirable or not.
Are you about to draw a push and you have Hydroblast in hand but they have a red creature and a problematic red permanent for example.


<!--
A bit expensive but great against control and also in fair matchups that don’t swarm with creatures, so it feels more widely applicable than Court of Cunning and other anti-control cards.
As it can tap Elvish Reclaimer and a Marit Lage created on the opponents turn and  is immune to Maze of Ith, it also feels useful against lands as long as you get to 3 mana.
2UB, 4 Loyalty: too expensive but we usually use the Ninjutsu 1UB: Preferably return a Nethergoyf or Tamiyo to your hand to put it directly into play, bypassing countermagic. As this deck is low on lands and uses Wastelands for tempo, 2UB is too much so you hardcast it. On MTGO, make sure to enable stops in your block (if you prefer to hit for 3) and combat damage phases (if you want to hit for more) so you won’t miss your window to use this!
During your turn, Kaito is a 3/4 creature with hexproof. Together with the -2, this static ability makes him extremely hard to be killed by opponents who don’t swarm the board with creatures. Other than getting attacked, the only common ways to remove him are REB, Brazen Borrower, Leyline Binding, Prismatic Ending for 4, Sheoldreds Edict, Teferi + Sweeper, Brainstorm + Terminus.
+1: Get an emblem giving all your Ninjas +1/+1. It only buffs Kaito but it stacks and if you always use it, he does 3/8/14/20 damage cumulatively.
0: Surveil 2, then draw a card if an opponent lost life this turn, Draws cards and the surveil helps Nethergoyf, Frog, Murktide, Counterbalance (if you keep both) and Tamiyo -3. 
-2: Tap target creature and put a stun counter on it. If the opponent has only one creature, you can 4->2->3->1->2->0 and tap it for 6 turns after which Kaito dies and you did 21 damage. 
-->

<!--
<mtg-card name=""/>
-->

### Niche Cards
<mtg-card name="Mishra's Bauble"/>
<mtg-card name="Dauthi Voidwalker"/>
<mtg-card name="Baleful Strix"/>
<mtg-card name="Stock Up"/>
<mtg-card name="Hymn to Tourach"/>

* Mishra's Bauble is great with Nethergoyf but Nihil Spellbomb is needed right now

### Dauthi Voidwalker
Easy for Izzet to remove but still a must deal with card early on, probably not the right choice for a bolt meta.
Insane against certain decks.
I [Minyafriend] have cast The One Ring and Karn against Forge, Sheoldred against Doomsday, Maelstrom Wanderer against Mississippi river, Undercity Informer with Faerie Macabre in hand against Oops, Doomsday against Doomsday.
It allows you to protect your own play if Force of Will is exiled, Fable of the Mirror-breaker spamming your own Bowmasters, just use your imagination.
The floor is pretty good and the ceiling is crazy high.
Best friends with Thoughtseize and counterspells.

Eco:

* Dauthi Voidwalker: I like this card because it’s never a bad draw and some decks HAVE to remove it. You have to play this on TOP of your normal graveyard hate because it doesn’t let you keep more hands vs. Oops.
* Stock Up: If the format slows down significantly, we can play this card. For example if Beanstalk becomes a good deck.
* Baleful Strix: Same philosophy. If we have to play a lot of mirrors and grindy matchups, Strix is good.
* Hymn to Tourach: Time has mainly passed on this card. I think decks like Show and Tell would have to be 20% of the meta game for Hymn to be good. These days, we have to play to the board a lot.
* 2nd Sewers: If you play a slightly bigger version with 20 lands, I like 2nd Sewers.

## Sideboard

<mtg-card name="Harbinger of the Seas"/>
<mtg-card name="Consign to Memory"/>
<mtg-card name="Hydroblast"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Grafdigger's Cage"/>
<mtg-card name="Cursed Totem"/>
<mtg-card name="Counterbalance"/>
<mtg-card name="Damping Sphere"/>
<mtg-card name="Engineered Explosives"/>
<mtg-card name="Force of Negation"/>
<mtg-card name="Null Rod"/>
<mtg-card name="Pithing Needle"/>
<mtg-card name="Spell Pierce"/>
<mtg-card name="Flusterstorm"/>
<mtg-card name="Subtlety"/>
<mtg-card name="Thoughtseize"/>
<mtg-card name="Toxic Deluge"/>
<mtg-card name="Tsabo’s Web"/>

Eco:

* Hydroblast: Look at combined amount of Moon, Sneak (not Omni), red Daze, red Painter and red Storm. I’ll play 0-2 copies depending on the meta game share.
* Consign to Memory: After Eldrazi’s ban, this is mainly a hate card for Mystic Forge. It also helps vs. Painter, Lands and D+T, so the combined amount of those + Forge is what you need to think about. 
* Cursed Totem: This card is viable if your meta game has both Cradle Control, Breakfast and Bant Nadu - maybe with some bad decks like Goblins (Skirk Prospector) or old school D+T (Mother) mixed in. Two mana is a lot for a niche card.
* Counterbalance: I liked this card quite a bit in Izzet where you also have Channeler to manipulate your top card. Furthermore, Dimir has a wider range of MV which makes Counterbalance less reliable for the cheap MVs. We also want to fetch swamp sometimes (Izzet plays 0 mountains), so UU is rough.
* Damping Sphere: Maybe some combination of 12-post, Forge and Storm can warrant this card.
* Engineered Explosives: I mainly view this as Chalice removal that can randomly kill Rhinos, Constructs or Empty goblins.
* Force of Negation: Great card to fight Show and Tell, Chalice, Forge, Storm and other combo decks. Always worth 2 slots for me.
* 1B removal: My current favorite is Edict which can kill walkers (mainly Tamiyo and Karn, but also against bad decks with Teferi and Narset) and doesn’t give bonus to Nadu. It sometimes can’t kill the Murktide on the field which is a shame. The other ones have to do with the amount of Voidwalker/Bombardier/Brazen vs. Dreadnought/Painter/Constructs in your meta.
* Harbinger of the Seas: I love this card. It punishes bad mana bases out of control, Breakfast and Sagas (not for long). (this was written before the rules change)

* Graveyard hate: Online, I like focusing on graveyard hate that lets me keep hands on the draw vs. Oops (Faerie, Surgical, Leyline). In paper, you can play your Cages to have crossover against Zenith.
* Null Rod: Great card these days. Mystic Forge is top8’ing every week, and Oops’ sideboard plan is now Belcher. It also beats bad Storm decks.
* Pithing Needle: This is a good one that will always find a use. Saga, Nomad, Ring, Lands etc etc. It’s often good deck building to play it.
* Spell Pierce/Flusterstorm: I don’t like the one-mana counters because they force me to hold up mana. Every mana unused in today’s Magic gets you closer to losing. Forces, Daze and Thoughtseize will cover for me.
* Subtlety: If the meta game was heavy Oops AND had a stompy deck with Cavern, I like this card.
* Thoughtseize: Playing 4th Thoughtseize in the sideboard will often be bad deck building. It’s fine in a lot of places, but will never shine enough to warrant a sideboard slot. If you like it, play 4 in the main.
* Toxic Deluge: Combination of Cradle, D+T, Bant Nadu and some Energy in your meta game, and you can play this.
* Tsabo’s Web: As you mentioned, heavy amount of Lands with a shift back to Rishadan Port is what you need.

Minyafriend:
> I played a few challenges with Web and found it very underwhelming, main point is that Urza's Saga untaps level 1 because it doesn't have the other abilities yet.
> Current lands does not get punished enough by this card.
> Pithing needle seems better if you want to stay UB and stop land strats.

### Graveyard Hate
<mtg-card name="Grafdigger's Cage"/>
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Faerie Macabre"/>
<mtg-card name="Ghost Vacuum"/>
<mtg-card name="Unlicensed Hearse"/>

|                     | turn | stops Oops completely | side benefits                                                                                                                                                                                           | counterplay                                     |
|---------------------|------|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| Leyline of the Void | 0    | yes                   |                                                                                                                                                                                                         | enchantment removal, bounce                     |
| Faerie Macabre      | 0    | no                    | Can be found with Barrowgoyf, combat trick for Nethergoyf, the only card that does not care about Teferi.                                                                                               | discard, Stifle                                 |
| Surgical Extraction | 0    | no                    | Also good against Life from the Loam and Uro, combat trick for Nethergoyf, in rare cases discard and win condition library removal. Can be bought back by Tamiyo.                                       | discard, countermagic                           |
| Nihil Spellbomb     | 1    | depends               | Cantrips. Great support to kill opposing Dragon's Rage Channeler's and Nethergoyfs. Can prevent Murktide Regent.                                                                                        | EE on 1, artifact removal, bounce, countermagic |
| Grafdigger's Cage   | 1    | yes                   | Stops Green Sun's Zenith and Mystic Forge but not Living End and Beseech the Mirror! Also prevents them from reanimating out of your own graveyard but also stops your own Nethergoyf from coming back. | EE on 1, artifact removal, bounce, countermagic |
| Ghost Vacuum        | 1    | no                    | Win condition in the rare case you get to 6 mana. Often prevents Delirium and Murktide Regent.                                                                                                          | EE on 1, artifact removal, bounce, countermagic |
| Unlicensed Hearse   | 2    | no                    | Can eventually attack and block so you don't risk overboarding against hybrid decks. Almost always prevents Delirium and Murktide Regent.                                                               | artifact removal, bounce, countermagic          |
| Dauthi Voidwalker   | 2    | yes                   | Also a clock and can use their opponent's cards against them. Keeps Dragon's Rage Channeler and Nethergoyf small and prevents Murktide Regent if played early enough.                                   | creature removal, bounce, countermagic          |

* Grafdigger's Cage Graveyard hate that also hits Green Sun’s Zenith and Natural Order like Elves, 5c Zenith, Nadu Zenith, Cradle Control (except Grist). I don’t like it that much against UB Reanimator because it gets hit by both Brazen Borrower and Keg/Explosives/Sylex, and we can’t kill them quickly, so as long as UB Reanimator is >20% of the meta and GSZ decks have a low play rate I’d rather play one of the other options. It's also one of the few cards that completely shuts down 
* Nihil Spellbomb: Mostly played in the main deck because it replaces itself and pumps Nethergoyf but you could also put it in the side.

## Not Recommended Sideboard Cards

<mtg-card name="Winter Orb"/>
<mtg-card name="Winter Moon"/>
<mtg-card name="Emrakul, the Aeon's Torn"/>
<mtg-card name="Court of Cunning"/>
<mtg-card name="Court of Locthwain"/>
<mtg-card name="Liliana of the Veil"/>

As someone who experiments a lot with off meta sideboard cards I want to tell you what doesn't work to make future exploration easier.

* Winter Orb and Winter Moon

Eco:
> Winter Orb used to see play out of aggressive daze decks to force the opponent to play on your terms while you attack them with a Delver. These days, Blue/Black Tempo is closer to a Midrange deck and can’t take advantage of it - mainly due to Tamiyo’s clues and 3-drops. 

> Winter Moon is interesting but very unreliable between opposing basics, Mox Diamond and your own need to fetch duals I’m certain games. Add in the fact that multiple Boseijus see play, and you end up with a very temporary false sense of security against Lands.

* Emrakul or any other shuffle Eldrazi: I tried this out after I played against 2 Painter opponents in the same league and then didn’t face any for the next three leagues…
* Court of Cunning: Former anti-control card but probably not needed anymore after Kaito.
When Pyroblast was popular I tried Court of Locthwain and Ravenloft Adventurer for 3 leagues but they never did anything and the Adventurer even lost me a game where my opponent just Pyrogoyfed my creature and won with the initiative. 
* Liliana of the Veil: Not powerful enough anymore.

## Variations

Eco on the red splash:
> I want to splash red if I go to Italy and play paper.
> Haha. I loved this splash when Show and Tell and Stock Ups were heavily played. Let’s say Painter became a 15% deck, then I would love Meltdown as well.

## Comparison to red-based Delver decks
Red-based Daze decks with Delver or Cori-Steel Cutter are more explosive and kill faster, have reach through Lightning Bolt and bring powerful red sideboard cards like Pyroblast and Meltdown.
UB Tempo is slower, has a more stable mana bases, can go longer through card advantage with Tamiyo and can kill high toughness creatures easier with black removal spells.

## Strategy

### Bauble trigger
In paper, I represent bauble triggers with blank cards to not forget them. 

### Early game
In most matchups, Tamiyo is the best T1 play in a vacuum while Nethergoyf can also be good on T2 because it doesn't do much dmg T2.
However because Tamiyo is so strong in fair blue mirrors, it can often be better start with something else like Thoughtseize to clear away a removal spell or Ponder for a Brainstorm or Daze so that you can protect Tamiyo better.
Also sometimes a t1 Nethergoyf can die to damage line bolt or Bowmasters.
Bowmasters t2 is good against decks that don't have their own Bowmasters. Ideal curve is Tamiyo Bowmasters Kaito.
Against combo you need to know the earliest they can reasonably win so e.g. vs oops you can never tap out for Tamiyo but vs sneak show them T1 combo is improbable so T1 Tamiyo is good. 

### Late game
For a Tempo deck you have a surprisingly good end game when Tamiyo and Kaito draw you extra cards which against some decks let's you just out control them once you stem the initial onslaught. 

## Clock Management

Eco:
Playing fast is important because it lets you slow down and take your time with hard, game-deciding decisions.
Practice your Ponders, land drops, short cuts and using F6 at strategic moments where you don't give up bluff equity.
It's the same in paper; play fast (and make your opponent play fast as well using the judge) from turn 1 of the game.
We should not cheat with slow play and then when game two finishes with 8 minutes on the clock start playing fast there.

## General Deck Advice

Traditionally you would wait with your spells to get the best result, e.g. wait if you really need to push an opponents creature or something else comes.
However this deck is quite mana hungry with all the cards you draw and the clues to crack, so it may often be correct to be quite liberal with your spells to maximize mana efficiency.
Even if you don’t suspect your opponent is on nonbasic land hate it is often almost free to get basic swamp and basic island so always consider this even if you think it unlikely.
A great game plan of this deck is to stick an early Tamiyo and then protect it and disrupt the opponent with Wasteland, Force, Daze and removal.
Nethergoyf doesn’t really fit that plan but it is the only card that really does damage early which can actually end the game reasonably fast other than Murktide which comes later.
This deck is super fun but is also hard to play, you need a lot of practice and care not to timeout, it is much more value focused and slower than Delver.

Minyafriend:

I do not agree to liberally fetch basics.
It hinders your ability to double spell and makes Wasteland much better late in the game.
Basics are a trap in this deck but a necessary evil due to Blood Moon.
If you play Harbinger, then you have to consider the Swamp at some point.
This is thinking that deserves nuance but I think more often than not we are hurting ourselves with fetching basics.
Wasteland is often more important as a mana source for clues than to pick off an opponent's land, we want to draw clues and ninjitsu Kaitos and cast Barrowgoyfs.
Wastelanding can open ourselves up to Daze, wastelanding can seriously harm our progression.
I need to smell blood or have good information to blindly wasteland the opponent.

## Own Card Guide
<mtg-card name="Nethergoyf"/>
<mtg-card name="Fatal Push"/>
<mtg-card name="Shoot the Sheriff"/>
<mtg-card name="Go for the Throat"/>

### Nethergoyf
Normally you want to attack first and then cast your spells to get more information but Nethergoyf often prefers the other way around so if you spells get countered you may attack for more.
Sometimes you don’t have a land in the graveyard and it’s good to fetch before attacking.
Against damage based removal, consider delaying Nethergoyf until it survives. For example T1 Ponder, T2 Brainstorm fetch Nethergoyf plays around Lightning Bolt. Alternatively you can also just fetch and Ponder and bait them into bolt, then save it with an instant.
You can force a delirious DRC to attack, then clear their graveyard with Nihil Spellbomb in the attack step, then block and kill it with Nethergoyf.
Don't forget the escape ability, as long as you don't have a Grafdigger's Cage in play.

### Fatal Push

Try to leave a fetch land or bauble uncracked if 3 and 4 mana creatures like Nadu are relevant in the matchup.
Against Moon Stompy, Fatal Push is often useless as you can not fetch with a Blood Moon in play, so consider leaving a clue uncracked as long as you don't play Null Rod. 
You can target any creature with Fatal Push, even if it doesn’t have an effect.

### Shoot the Sheriff
Does not hit Brazen Borrower and Broadside Bombardiers. 

### Go for the Throat
Relevant artifact creatures: Constructs, Painter’s Servant, 

### Sheoldred's Edict

Kaito is not a planeswalker on the owners turn, you need to choose creature in that case!
So if they have an additional creature you need to wait until your turn to remove it.
Creatures with Flash can make it unreliable, like Orcish Bowmasters, Endurance or half of Death and Taxes.

### Brainstorm
Flipping Tamiyo T2 means a T5 ultimate if not stopped  which mostly wins the game.
Don't forget to play around Orcish Bowmasters.

### Murktide Regent
The current meta is high on fatal push which is why Murktide is often a great counter to the meta removal.

### Counterbalance
Personal pet card but I don't play it without Delver because you don’t have 4 DRC and 4 Mishra’s Bauble, so you only have Brainstorm (reactively), Ponder (proactively), and Fetchland + maybe Scryland (hopefully).
It’s great against all kinds of blue cantrip decks, whether it’s combo, control or tempo.

### Nihil Spellbomb
Great T1 nonsense protection in the current meta. Even if you see them as something else online, everyone seems to play Reanimator now.
Doesn't stop LED -> Echo.
Prevents Murktide, shrinks DRC to block it or kill it with Bowmasters. 

## Opponent Card Guide

### Gaea’s Cradle
<mtg-card name="Gaea's Cradle"/>

Sometimes they have a dual land and a Gaea’s Cradle in play and you have to consider which to Wasteland, don’t always automatically kill Cradle as you might be able to mana screw them completely if they have no land in hand, though it is dangerous against decks with a lot of one drop creatures like Elves.

### Urza’s Saga (outdated by rules change)
<mtg-card name="Urza's Saga"/>
I don’t know why most people don’t do this, but I almost always bring in my Harbingers of the Sea against Saga decks because having a 3 mana 2/2 that kills a Saga and does more later is really strong on it’s own as long as you remember to fetch basic swamp beforehand.
You can Wasteland it with the first trigger on the stack so they never get mana.
You can Consign to Memory any of the chapter abilities but not the activated one to create a token.

### Crop Rotation
<mtg-card name="Crop Rotation"/>
Most of the time it's correct to force it, Wasteland on the opponents turn if you have FoN in hand, even if they have no mana, they may play Elvish Spirit Guide.

### Timing Guide

* Bowmaster their Bowmaster
* Fetch in response to fetch against Stifle
* Daze Wasteland trick


## Play Patterns

### Shrinking and Growing Creatures

<mtg-card name="Nethergoyf"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Murktide Regent"/>
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Dragon's Rage Channeler"/>
<mtg-card name="Tamiyo, Inquisitive Student"/>
<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Undercity Sewers"/>

Both UB tempo and many other meta decks have lots of variable-sized creatures, mostly related to card types in the graveyard.

Examples:

* Nihil Spellbomb + Orcish Bowmasters kills Nethergoyf
* Nihil Spellbomb + Murktide Regent + Orcish Bowmasters kills Barrowgoyf
* Nihil Spellbomb + ground blocker kills a formerly delirious Dragon's Rage Channeler
* grow Murktide with second Murktide, Nihil Spellbomb, Faerie Macabre or Tamiyo -3

Undercity Sewers can be a hail Mary to hope for a favorable flip or you may even guarantee it with a Brainstorm.

-> insert pictures here

### Threats First or Later

<mtg-card name="Thoughtseize"/>
<mtg-card name="Tamiyo, Inquisitive Student"/>
<mtg-card name="Ponder"/>
<mtg-card name="Nethergoyf"/>

If you come from a control background you probably prefer to set up with cantrips early but early threats can snowball the game much better, especially Tamiyo.
Of course this heavily depends on the matchup, for example vs Oops your best T1 play is Nihil Spellbomb and your second best is Thoughtseize.
If you are on a single blue source, think about how probable it is that you get Wastelanded depending on what the opponent shows you.
Orcish Bowmasters are often better later in Bowmaster mirrors but against decks with no removal like Show and Tell main phasing it as early as possible is often good.

## Matchups

The deck is generally good against linear combo and red-based tempo decks but struggles against bigger fair decks.

### UB Reanimator (20% Meta game)

<mtg-card name="Reanimate"/>
<mtg-card name="Entomb"/>
<mtg-card name="Atraxa, Grand Unifier"/>
<mtg-card name="Archon of Cruelty"/>
<mtg-card name="Tamiyo, Inquisitive Student"/>

The currently most played and probably strongest deck even after the Grief, Frog and Troll bans is a tempo combo hybrid that puts you in constant danger from two angles:
If you keep or even mulligan to a hand with grave hate and Force of Will, they may just out-tempo you with Tamiyo, Orcish Bowmasters, Murktide Regent, Brazen Borrower or Barrowgoyf.
If you have threats and removal they may just reanimate a Fattie and against tempo the game is mostly over if a single Fattie hits the battlefield.
However since the Frog ban, the tempo part of the deck is much weaker, especially before sideboarding, so you should prioritize not dying to their combo and your tempo plan will most likely win against theirs.
Very skill testing, but good matchup for us if we have two Nihil Spellbomb in the main deck, just be prepared to fight over end of turn Petty Theft into their turn Reanimate.
They have a sideboard juke to board out Entomb, Animate Dead and the Fatties and board in more creatures like Barrowgoyf and more removal.
However then they are just a worse tempo deck than you are so it’s probably best for them to not juke, unless they expect you to over-prepare for the reanimation plan.

Before the Grief ban, graveyard hate from hand was bad due to Grief but I often get my Grafdigger’s Cage bounced by Brazen Borrower or killed by Engineered Explosives and lose anyways. Since the Grief ban your hand is a bit safer so cards like Surgical Extraction and maybe even Faerie Macabre should be better now.
It’s also super hard to win two games in a row on the play and draw, so having mainboard grave hate like Nihil Spellbomb really helps.

Minyafriend:

> Identify what kind of UB Reanimator you are playing against.
> Do they have push main, Inquisition of Kozilek in the sideboard, they go harder on combo, no midrange plan other than Tamiyo, no Bowmasters?
> Are there Murktides and Barrowgoyfs main? Then it's midrange with I-win-button.
> Stifles and Murktides main indicate tempo/combo.
> Voidwalkers main usually read as UB Reanimator, probably midrange sideboard plan.
> Are they a Wasteland version?
> Definitely heavily recommend looking up opponents in challenges to see what style they are known for and make decisions accordingly.
> This deck has A LOT of options to build around.
> I don't recommend siding out Force of Will even with Dauthi Voidwalkers.

#### Sideboarding:

<mtg-card name="Grafdigger's Cage"/>
<mtg-card name="Faerie Macabre"/>
<mtg-card name="Sheoldred's Edict"/>

In: All graveyard hate (normally I have 2 mainboard and another 2 sideboard).
Don’t board in FoN as it’s not good against their fair plan and also avoid Consign to Memory, as they probably board out Animate Dead.

Out: Shave Daze, Wasteland, maybe 1 Fatal Push if you don't see Voidwalkers. All Barrowgoyfs as they are too dangerous to get reanimated against you.
I used to board out 4 Wasteland but you need the mana against Daze and to crack clues and you want to keep them below 5-6 mana for hardcast FoW, and the Ghost Vacuum in case they being that in. 

Alternative: If you have 4 mainboard Dauthi Voidwalker, you can board out Force of Will instead and keep Barrowgoyfs.

### UB Tempo Mirror (6% Meta game)

Luke:

#### Sideboarding
Thankfully, the sideboard plan for the mirror is straightforward and intuitive.

##### Out
<mtg-card name="Force of Will"/>

-4 Force of Will.

In the mirror, we share most cards with our opponent, depending on whether they have elected to configure their deck around Dauthi Voidwalker or Nethergoyf. There are no "unfair" or "win the game on the spot" combos out of the UB Tempo deck, so the resulting matches are attrition style, back and forth games. Force of Will is a liability due to the requirement of exiling one of our other cards. We will replace them with cards that deal with threats after they have hit the board, as well as some additional threats of our own.

##### In
+2 Barrowgoyf
+2 Removal.

<mtg-card name="Barrowgoyf"/>
Barrowgoyf has been discussed at length in this guide, and I will address its merits again shortly.

<mtg-card name="Sheoldred's Edict"/>
<mtg-card name="Bitter Triumph"/>
<mtg-card name="Dismember"/>

I will focus the majority of this section on removal spell choices.
There are numerous options for removal spells in black. As of the writing of this contribution (July 2025), I believe Sheoldred's Edict is the best option, and have two copies in my sideboard. Now, I will outline the pros and cons of the various removal spells as they relate specifically to the UB Tempo mirror.

<mtg-card name="Sheoldred's Edict"/>

Let's take a look at some of the things that Sheoldred's Edict answers:

<mtg-card name="Tamiyo, Seasoned Scholar"/>
<mtg-card name="Kaito, Bane of Nightmares"/>
<mtg-card name="Murktide Regent"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Orcish Bowmasters"/>

* Flipped Tamiyo: Something that will end the game if not answered, or at the very least, accumulate value with the pseudo-regrowth effect and create a sub-game that takes pressure off of life total. 
* Kaito (creature): Kaito has hexproof during the controller's turn, so Sheoldred's Edict is the only 2 mana removal spell I have included in this section that offers an answer to Kaito in creature form. This relies on the opponent not having any other non-token creatures in play, so be cautious if they have 2 mana available. It would be disastrous to have your edict blown out by a Bowmaster when you could have just waited until your own turn to have them sacrifice a planeswalker.
* Kaito (planeswalker): Although it is not ideal, sometimes you just have to make a play because it is the only one available to you. There will be times when you or your opponent will have to cast Kaito for 4 mana and pass. If you have the edict and the mana for this particular case, and they don't have another non-token creature, great, you've just made their lack luster play even more embarrassing. If not, and you find the edict in your draw step or with a cantrip, the chances of the sacrifice a planeswalker mode working are quite high, but not 100%. If they have Tamiyo in play, an open blue mana, and 1 card in hand, it is in the realm of possibility that they flip the Tamiyo and sacrifice it to save Kaito. If you have a creature that may have pressured they Kaito, they likely will have used the -2 ability to stun it to take the pressure off of Kaito while they look for a way to protect it or develop their own board. This is where edict provides a clean answer to Kaito in planeswalker form.
* Murktide: Murktide cannot be removed with Fatal Push, leaving 3-4 temporary answers in the form of Kaito -2 and Petty Theft if you are not lucky enough to snipe a Murktide with Daze or Thoughtseize. Sheoldred's Edict can remove Murktide, but be cautious of instant speed Bowmasters. You may be required to use your push, Petty Theft, and Bowmasters to clean up any non-token creatures in order to kill the Murktide with edict.
* Barrowgoyf: Barrowgoyf is a must-answer threat. It provides large life total swings, trades with anything that blocks it, provided there is at least 1 card among both graveyards, fuels the yard for Murktide, and can provide card advantage by finding additional threats. Thankfully, there are more answers to Barrowgoyf than Murktide in the mirror. Revolt is reasonable to gain access to thanks to Wasteland, fetches, clue tokens, etc, so Fatal Push is often live against Barrowgoyf. Sheoldred's Edict works much the same as an answer to Barrowgoyf as it does to Murktide, and the same precautionary measures should be taken.
* Orcish Bowmasters: If you are in dire circumstances, Sheoldred's Edict offers a choice to remove either the Bowmaster, or a large orc army token that may have grown as a result of desperation digging with Brainstorm or Ponder. You have to do what you have to do, and win is a win, whether you crushed your opponent or barely clawed your way to victory. In the UB Tempo mirror, you are more likely to encounter the latter.

<mtg-card name="Dismember"/>
Dismember is a card that I have seen others play in the past as a way to deal with a resolved Magus of the Moon in 3+ color decks without access to a basic swamp. This is an insufficient argument for the inclusion of Dismember when we have access to one of each basic in our colors. I find Dismember to be unreliable in killing Murktide and to a lesser extent, Barrowgoyf. It is worth mentioning that Dismember can be used as a combat trick to allow your creatures to survive and set up favorable trades, or in combination with a timely Bowmaster ping to remove a 6 toughness creature.

The urgent nature of an early Tamiyo and the presence of Daze often results in casting Dismember for 1, which is a nice option, but the reduction in your life total cushion is felt in late game scenarios where you need to push for lethal or cantrip into an active Bowmaster to find lethal or an answer to an impending threat. Lastly, Dismember cannot kill Kaito or a flipped Tamiyo. For these reasons, I do not play it.

<mtg-card name="Bitter Triumph"/>
Bitter Triumph plays a bit like a compromise between Sheoldred's Edict and Dismember. It has the greatest flexibility in what it is capable of answering, and is the only 2 mana removal spell discussed in this section that can remove anything out of the UB Tempo deck, no questions asked, save for creature-Kaito during an opponent's turn. There is value in having access to a removal spell that you know can remove whatever you need, but this comes at a cost of either discarding a card, or 3 life. I mentioned earlier that Force of Will is a liability in the mirror because it is necessary to exile another card in hand in order to cast for free. This is also true for the "discard a card" additional cost for Bitter Triumph, but without the benefit of being able to cast it for free. Once you reach a comfortable number of lands in play, you will likely want to sand bag one to improve future Brainstorms. This could offer an alternative to paying life for Bitter Triumph, but at the cost of making said Brainstorm worse.

I have played with Triumph in the past, and almost always ended up paying life. This is problematic in late game scenarios when you need those last few life points to survive. The final scenario is a bit extreme, but it is necessary to identify the fail cases of cards when determining what to include in your 75. Imagine your opponent plays 2+ power creature. You have no cards in hand, no creatures in play, and are at 2 life. Your opponent passes, and you draw Bitter Triumph. You cannot even cast the Triumph and are dead next turn. This would not happen in most other scenarios if the other removal spells were drawn instead.


<mtg-card name="Shoot the Sheriff"/>
<mtg-card name="Go for the Throat"/>
These two cards are essentially the same, and reminiscent of Doom Blade, in that they ask "What kind of creature are you fine with being unable to kill?" While there are many examples of creatures in Legacy that one or the other cannot kill, there are some major ones. Shoot the Sheriff cannot kill Dauthi Voidwalker or Broadside Bombardiers, and Go for the Throat cannot kill Construct tokens. If you should decide to play Shoot the Sheriff or Go for the Throat in your 2 removal sideboard slots, those are the main creatures to look out for. Your local meta will inform your choice. I strongly urge you against playing these cards over Sheoldred's Edict or Bitter Triumph, especially in the context of the UB Tempo mirror.

I rank the removal options as follows, from best to worst: Sheoldred's Edict > Bitter Triumph > Go for the Throat / Shoot the Sheriff > Dismember


### Discerning Reanimator and UB Tempo

It's sometimes hard to know whether you are versing the mirror or UB Reanimator after G1 unless you see Nethergoyf, Kaito or mainboard Fatal Push (UB Tempo) or Entomb, Reanimate, Atraxa, Archon of Cruelty or Animate Dead (UB Reanimator).
The second Undercity Sewers is also an indicator but not always. 
When in doubt it’s better to assume Reanimator if you aren’t sure because it is played so often but I would not shave on Fatal Push then.

### Oops All Spells

This is one of the few matchups where I mulligan aggressively for turn 1 interaction they are so fast.
Take your time, mulligan to enough turn 1 interaction and never give them an opening to combo.
Double Daze + Surgical is not enough on the draw as the zombies will kill you in three turns after memories journey even if you surgical the Thassa's Oracle.



#### Sideboarding

##### In

<mtg-card name="Grafdigger's Cage"/>
<mtg-card name="Faerie Macabre"/>
<mtg-card name="Force of Negation"/>
<mtg-card name="Consign to Memory"/>
<mtg-card name="Null Rod"/>

Bring in all graveyard hate and countermagic including Force of Negation and Consign to Memory.
With Force of Negation you may have to force Dark Ritual because their combo pieces are creatures.
They may have a pivot to creatures (if you don't see Pact of Negation) or to Goblin Charbelcher, but that is not great for them because your countermagic still works against it, often they still do it so bring in the Null Rods.

Null Rod, 

#### Out

<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Fatal Push"/>

Shave Wasteland if that isn't enough.

### Dragon Stompy

Slightly unfavored matchup but can be beat by fetching basics ASAP and focusing on staying alive through the early turns.
Hopefully they run out of haymakers before you run out of answers.
Hydroblasts and Consign to Memory are most important here but Goyfs are great as well.
Null Rod?

Minyafriend:
> Not a big fan of Null Rod. Try not to get your Goyfs Furied but what can you do.

### Lands
Bad matchup but can sometimes be beaten by Harbingers of the Seas, hopefully they don't stick a Saga on 2 before that enters.

#### Sideboarding
Force of Negation is good because it prevents Life from the Loam from coming back.
Similarly if there is a lot of lands it may be worth it to switch one of your graveyard hate pieces to Surgical Extraction.
A single Surgical is a nice against Loam and as you have so many dead cards like Push and Bowmasters it is surely better than those and can get rid of some other card as well in a pinch.
Harbinger is still great, you may just need to Wasteland a Saga first in some spots which complicates things a bit.
Consign to Memory is not great but still better than Bowmasters and Push, it can counter an artifact or a Saga Trigger or maybe Bojuka Bog or something else.
You can try Tsabo's Web if it is a lot of lands (never tried it though).

### BUG Beans

<mtg-card name="Up the Beanstalk"/>
<mtg-card name="Rakshasa's Bargain"/>
<mtg-card name="Witherbloom Command"/>
<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Murktide Regent"/>

Super fun to play and much loved by the community but even with the new Rakshasa's Bargain it does seem to compete at the absolute top of the meta game right now so the play rate is currently not that high.
Theoretically it is built to counter Tempo decks such as UB because it has more value while still having enough threats to not being clunky, but due to the high power level of the current UB cards it is still somewhat even, as Tamiyo or Kaito can often outvalue them if they don't have multiple Beans out.
A flipped Tamiyo can easily be killed by Witherbloom Command but Kaito is very hard to stop for them, as they usually only play a single Sheoldred's Edict, so focusing on T3 Kaito is often a great path to victory, for example by starting with basic Island and Swamp so that they can't delay Kaito with Wasteland.
There are different variations with a lot of potential one or two-offs so keep in mind what they could have, such as Spell Pierce, Daze, Stifle, Wasteland or Endurance, but don't overrespect them because you are the aggressor and the chance of them having any such particular card is low.

Minyafriend:
> I do bring in Force of Negation at the very least on the draw as you will be up a card already and you really do not want Beanstalk or Carpet to resolve.

#### Sideboarding

After boarding, prevent Carpet of Flowers at all costs, then you may be able to Tempo them out or lock/kill them with your additional nonbasic hate of choice (Harbinger, Price of Progress, ...).
Fortunately they don't usually play more than one or at most two Carpets in the Sideboard, which I don't understand because this card can single handedly win vs Tempo.

##### In

<mtg-card name="Sheoldred's Edict"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Harbinger of the Seas"/>

Sheoldred's Edict is much more flexible than Fatal Push because it can also kill Murktide and a flipped Tamiyo.
We don't board in Force of Negation because it's too much card disadvantage and they play a lot of creatures too.
As always, replace Harbinger with your other nonbasic hate of choice if you have it, such as Price of Progress with a red splash.
Against nonstandard variations with 3-4 Uro instead or in addition to Murktide you may board in a Surgical extraction if you have it.

##### Out

<mtg-card name="Daze"/>
<mtg-card name="Fatal Push"/>
<mtg-card name="Brazen Borrower"/>

Fatal Push is bad against most of their deck but depending on your other removal you may need to keep two in depending on how many Tamiyos and Endurances they play.

Eco:
> Brazen is fine vs Beanstalk if you’re happy waiting for the Murktide to show up. You can keep it

### Jeskai Control
Very bad matchup but fortunately not widely played.
It sucks to keep Fatal Pushes in but 2 are needed against Tamiyo.

### Black Saga Storm (~ 1% Meta game)

<mtg-card name="Dark Ritual"/>
<mtg-card name="Mox Opal"/>
<mtg-card name="Lion's Eye Diamond"/>
<mtg-card name="Beseech the Mirror"/>
<mtg-card name="Gaea's Will"/>
<mtg-card name="Tendrils of Agony"/>
<mtg-card name="Echo of Eons"/>
<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Urza's Saga"/>

Super difficult to play against as they have so many different threats and you never know what they are up to this game.
Nihil Spellbomb is often bad as they keep priority between sacrificing Lion's Eye Diamond and casting Echo of Eons.
Null Rods are very strong here, then you just need to beat the huge construct tokens, Engineered Explosives is also great.

- 4 Fatal Push, 2 Nihil Spellbomb
+ FoN, Consign, EE, 

Unfavored because we don’t have Delver and Bolt to close out games quickly and we also don’t run Counterbalance to lock up the game, so we give them lots of time.
They have compact kills like LED+Echo so just stopping them once often isn’t enough and they can also kill us with large constructs if we don’t immediately have Wasteland for Saga or with Echo + Bowmasters.
Can be vastly improved with 1-2 Null Rods.
Powder Keg/Filigree Silex/Engineered Explosives also helps but Powder Keg is the best as it also kills artifact lands.
After playing this matchup a lot I realized:
Nihil Spellbomb is not good enough as it only works against Gaea’s Will but not against Echo + LED due to the way priority works, so I switch them out for Grafdigger’s Cage in sideboarding (which doesn’t prevent Beseech but at least Echo).
Their Sagas are so deadly that I bring in 2 Harbinger of the Seas just to prevent that, it’s also often a lock with Null Rod.
 

### Quick Tips:
Most of the time it’s correct to counter Veil of Summer as they often play that into Echo + LED.
Tamiyo is an out to Empty the Warrens goblin tokens but it’s often hard to flip her if you don’t have Brainstorm and have a Null Rod in play as Clues are artifacts.
 Consign to Memory can counter multiple Saga triggers

#### Play Patterns and Interactions

##### Soft Lock
<mtg-card name="Harbinger of the Seas"/>
<mtg-card name="Null Rod"/>
If they don't already have big creatures or a Saga on 2. this soft lock can only be broken by Elvish Spirit Guide + Boseiju, Who Endures or double Bowmaster trigger.

##### The Nonbo
<mtg-card name="Null Rod"/>
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Clue"/>
Especially painful if you lose to Empty the Warrens and stop your own Tamiyo flip, I always board out Nihil Spellbomb though.

##### Stop the Wheels
<mtg-card name="Lion's Eye Diamond"/>
<mtg-card name="Lion's Eye Diamond"/>
<mtg-card name="Echo of Eons"/>
<mtg-card name="Echo of Eons"/>
<mtg-card name="Force of Will"/>
<mtg-card name="Faerie Macabre"/>
You don't get priority after a Lion's Eye Diamond activation before an Echo of Eons cast but at least you can exile one with the other on the stack and then counter the first.

#### Sideboarding

#### In
<mtg-card name="Force of Negation"/>
<mtg-card name="Consign to Memory"/>
<mtg-card name="Null Rod"/>
<mtg-card name="Engineered Explosives"/>
<mtg-card name="Grafdigger's Cage"/>

If you have nonstandard countermagic like Counterbalance, Flusterstorm, Spell pierce, Mindbreak Trap and so on of course bring it all in.

#### Out
<mtg-card name="Fatal Push"/>

#### Maybe
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Surgical Extraction"/>
<mtg-card name="Faerie Macabre"/>
<mtg-card name="Brazen Borrower"/>
<mtg-card name="Harbinger of the Seas"/>
<mtg-card name="Swamp"/>
<mtg-card name="Island"/>

I have played this match a lot against an excellent player and we could not come to a conclusion for the last few slots, so make your own decision based on your opponents variant, play style and play/draw.
The grave hate I rate Grafdigger's Cage >> Surgical Extraction > Faerie Macabre > Nihil Spellbomb.

#### Cards they may have MB or SB

<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Veil of Summer"/>
<mtg-card name="Elvish Spirit Guide"/>
<mtg-card name="Carpet of Flowers"/>
<mtg-card name="Boseiju, Who Endures"/>


* Their Plan: Beseech + Gaea’s Will, Echo + Tendrils, Echo + Bowmasters, Constructs, maybe Empty the Warrens


### ANT

Weaker storm deck in a vacuum but due to Cabal Rituals it does not fold to your Null Rod alone.

### Initiative Stompy



### Sneak and Show

<mtg-card name="Show and Tell"/>
<mtg-card name="Sneak Attack"/>
<mtg-card name="Emrakul, the Aeon's Torn"/>

Good matchup but can easily be lost if you misidentify the critical turn after which you don't tap out anymore.
Play too passive and you get buried by their Stock Ups but play too aggressive and they just combo you out.
I like a single Sheoldred's Edict as an out to Emrakul.
Unfortunately Kaito does not count as a creature in your hand so you cannot bring it in with Show and Tell.

##### In

<mtg-card name="Force of Negation"/>
<mtg-card name="Flusterstorm"/>
<mtg-card name="Hydroblast"/>
<mtg-card name="Surgical Extraction"/>

+ Hydroblast, FoN, Consign
+ 1 Sheoldred's Edict?
- Fatal Push

##### Out

<mtg-card name="Fatal Push"/>
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Baleful Strix"/>
<mtg-card name="Barrowgoyf"/>

### Show and Tell (Omni Tell)

The mono blue basic land variant is very hard to deal with as they ignore most of your preboard interaction (Fatal Push, Wasteland, Nihil Spellbomb) and puts you into the rare position that you may have blanks in your board after sideboarding.
Fortunately that version has a very low play rate as most include some nonbasics so you get value out of Wasteland.

#### Sideboarding

##### In

<mtg-card name="Force of Negation"/>
<mtg-card name="Flusterstorm"/>
<mtg-card name="Surgical Extraction"/>

##### Out

<mtg-card name="Fatal Push"/>
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Baleful Strix"/>
<mtg-card name="Barrowgoyf"/>

### Red Painter

### Blue Painter

### Stiflenought

### Eldrazi
<mtg-card name="Eye of Ugin"/>
<mtg-card name="Eldrazi Temple"/>
<mtg-card name="Kozilek's Command"/>
<mtg-card name=""/>

After the ban of Sowing Mycospawn, the deck is much less oppressive but still structurally favored due to Chalice of the Void and a long stream of large, potentially uncounterable threats.

In: Force of Negation, Consign to Memory and Harbingers of the Seas are good against both of them.
In: Consign to Memory, Force of Negation, Harbingers of the Seas
Out: 


### Planar Nexus Decks: Mystic Forge and Cloudpost Ramp
As ramp strategies they want to establish a giant mana advantage and then overwhelm you with game ending threats until you run out of Forces or they play Ugin, Eye of the Storms, and if they ever resolve The One Ring, they never run out of cards.
You can try to close out the game fast with Nethergoyf and Murktide while countering key spells but in my experience the best way to beat them is to stick Null Rod, respectively Harbingers of the Seas, and finish them after.
Similar to UB Tempo and UB Reanimator, the decks have lot of overlap, but in different numbers, that are hard to differentiate, but thankfully the same sideboard cards are good against both of them though in different degrees, so take that in mind for mulliganning post board and cantripping.
For example Null Rod is the key card vs Mystic Forge but still reasonable vs Cloudpost where Harbinger of the Seas is better.
Fatal Push is useless vs Cloudpost but may hit a Glaring Fleshraker vs Mystic Forge. 

#### Common Core
<mtg-card name="Ancient Tomb"/>
<mtg-card name="Planar Nexus"/>
<mtg-card name="Urza's Tower"/>
<mtg-card name="Urza's Workshop"/>
<mtg-card name="The One Ring"/>
<mtg-card name="Karn, the Great Creator"/>
<mtg-card name="Kozilek's Command"/>
<mtg-card name="Ugin, Eye of the Storms"/>

#### Karn Wishboard
<mtg-card name="Ensnaring Bridge"/>
<mtg-card name="Mycosynth Lattice"/>
<mtg-card name="Liquimetal Coating"/>
<mtg-card name="Pithing Needle"/>
<mtg-card name="Portable Hole"/>
<mtg-card name="Soul-Guide Lantern"/>
<mtg-card name="Tormod's Crypt"/>

#### Sideboarding
##### In
<mtg-card name="Force of Negation"/>
<mtg-card name="Consign to Memory"/>
<mtg-card name="Harbinger of the Seas"/>
<mtg-card name="Null Rod"/>
<mtg-card name="Sheoldred's Edict"/>
<mtg-card name="Brazen Borrower"/>

##### Out
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Fatal Push"/>
<mtg-card name="Orcish Bowmasters"/>
<mtg-card name="Daze"/>

Unsure if Daze is a better cut than Bowmasters (only good against the One Ring and may not be enough).

#### Mystic Forge (8%)

<mtg-card name="Mystic Forge"/>
<mtg-card name="Glaring Fleshraker"/>
<mtg-card name="Manifold Key"/>
<mtg-card name="Grim Monolith"/>
<mtg-card name="Tezzeret, Cruel Captain"/>

As long as it's play rate is that high, Null Rod and Consign to Memory have a lot of value in the sideboard.
Because of Glaring Fleshraker, removal may be more important than against Cloudpost but I think 2 Edicts should be enough.
If you land Null Rod, you need to be aware of Planar Nexus and Mox Opal making white mana for portable hole out of their sideboard / wishboard but they don't always play it.

#### Tezzeret, Cruel Captain
<mtg-card name="Tezzeret, Cruel Captain"/>

Recent addition, so the number of copies varies between 0 and 4.
Together with Karn this gives them a lot of interaction against Null Rod, Tamiyo and Bowmasters.
Unlike Karn, it tutors from the main instead of sideboard so you should be safe from Portable Hole preboard.
Unlike Urza's Saga, its tutor condition is based on mana value not mana cost, allowing Portable Hole and Walking Ballista (if they have it).

##### Mainboard Tutor Targets
<mtg-card name="Lotus Petal"/>
<mtg-card name="Manifold Key"/>
<mtg-card name="Voltaic Key"/>
<mtg-card name="Mox Opal"/>
<mtg-card name="Pithing Needle"/>
<mtg-card name="Soul-Guide Lantern"/>

##### Sideboard Tutor Targets
<mtg-card name="Portable Hole"/>
<mtg-card name="Tormod's Crypt"/>
<mtg-card name="Walking Ballista"/>


#### Cloudpost Ramp (<1%)

<mtg-card name="Cloudpost"/>
<mtg-card name="Glimmerpost"/>

Can have a green splash for Crop Rotation and sideboard Veil of Summer.
Harbinger of the Seas is the best card but try to setup a Force of Will in case they have Dismember post board.


### Bant Nadu

Minyafriend:
> Funnily enough Bant Nadu is a bad matchup.

Flodope from the other side:
> I would say as a Bant Nadu player I don't like very aggressive starts out of the UB tempo deck, like fast Nethergoyfs backed up by Wasteland and Orcish Bowmasters, which make my cantrips costly when I try to dig out of the situation, an early Grafdigger's Cage hurts.
> Sometimes I see toxic deluge boarded against me which is not so nice.
> Teferi can be very good but also quite awkward, I like additional Endurance against UB Tempo more than multiple Teferis, because they handle Nethergoyfs and can prevent Murktides.

### Cephalid Breakfast

<mtg-card name="Cephalid Illusionist"/>
<mtg-card name="Nadu, Winged Wisdom"/>
<mtg-card name="Nomads en-Kor"/>
<mtg-card name="Shuko"/>

#### Videos

<youtube-video id="cQAHgwzGWTA" t="120"/>

Minyafriend:
Breakfast I find to be pretty good as we are fairly well equipped to deal with their creatures.
Just pay attention to what their next turn could be and if you can play around it do so.
T2-T3 are sensitive times where you can just lose games you shouldn't out of the blue if you are careless.

#### Sideboarding

Games can go long so:
Out: daze In: removal

Their manabase is shaky so it is reasonable to think OTP daze can be useful.
Just pay attention to how the opponent plays.
I rarely if ever bring it in but is Consign considerable so you don't lose to saga tokens and Thoracle trigger?
If you play Harbinger then I would not bring consigns in.
I think you can beat this deck without the Consign but I'm starting to wonder, some breakfast players are even bringing in Soul Cauldron.

Eco:
> Against Breakfast, I don’t bring in graveyard hate any more (keeping Nihil is good) because every card in my deck is good against them.

##### In
<mtg-card name="Sheoldred's Edict"/>
Sheoldred's Edict is nice because it does not target so it can sometimes trade 1 for 1 with Nadu.

##### Out
I used to board out Nethergoyfs to go for a control play style with Harbinger as the finisher but after the Saga rules change this is more risky and is also weak into Teferi uptick + combo next turn.

### Hybrid Decks

Eco:

Breakfast / Tempo DD / Reanimator sideboarding:
These decks are good because they ask tough questions of their opponent.
Against Breakfast, I don’t bring in graveyard hate any more (keeping Nihil is good) because every card in my deck is good against them.
Thoughtseize, Push, Force, Bowmasters. Tempo DD with Tamiyo, Barrowgoyf and Murktide, I’ll have removal spells for + Forces.
Reanimator is the same logic; graveyard hate, removal spells and Forces.


### Doomsday




*TODO: update, this was written in frog times*
Its pure combo version, Turbo Doomsday is a fast and resilient combo deck where your classic tempo plan of early threats + disruption works well.
One of the few matchups where Grixis is much better as they don’t have Wasteland to punish a greedy mana base and Pyroblast, Lightning Bolt and Molten Collapse (hits Vexing Bauble, Tamiyo in both forms, and other creatures) are really good against them. Still, we are a tempo deck and they are a combo deck so we are still favored if we play tight.
Trying out Doomsday yourself really helps to understand what they try to do and how to prevent that.

However many Doomsday pilots choose to include tempo or control elements, which changes again after sideboarding, making sideboarding and playing against them a high-skill affair. It takes more skill for them to beat you but most Doomsday players are experts, so never underestimate them and always give your best at any moment, as they might surprise you and win at any time if you make a single mistake.

Online it is really important to look them up as seeing their exact decklist is crucial to best line up your cards with theirs. In paper at least you see most of their preboard configuration after Doomsday, though they might hide some critical card on the bottom of the pile.
If I know their sideboard includes lots of creatures, I assume they are bringing them in because they are at their best versus tempo, so I assume they are cutting combo cards.
While versions are on a spectrum, here are some general archetypes:

Turbo tries cast actual Doomsday at all costs with cards like Personal Tutor, Cabal Ritual and Vexing Bauble.
Control can include The One Ring and splash green for Veil of Summer (quite good against blue-black) and white for Teferi, Time Reveler.
Tempo is currently very popular and can partially or even completely sideboard out of the combo for creatures such as Tamiyo, Murktide Regent and finally Barrowgoyf, which mostly replaced Sheoldred, the Apocalypse.

In general you want to focus on creatures removal against tempo but reduce removal and
As sideboarding depends so much on their configuration, here are some card specific tips:

Counterbalance, Orcish Bowmasters and Tamiyo are amazing against all versions and should always stay/be brought in.
Murktide Regent can be cut against turbo as it attacks on T4 at the earliest where the Doomsday player may already have won.
Creature removal obviously depends on their creatures. It’s not worth bringing it in only against Thassa’s Oracle and hard cast Street Wraith. However in most cases they will bring in at least some creatures, so cutting all removal is very risky. Black removal mostly hits all their creatures, though 
Hard grave hate like Faerie Macabre is never worth it, though Surgical can be brought in as a hail Mary to shuffle their deck post Doomsday (or exile Doomsday after you discard or counter the first one) if they include so few creatures that you can sideboard out so much removal that you have nothing better to bring in. 
Value grave hate like Nihil Spellbomb and Unlicensed Hearse is only good against Murktide Regent, though it can also sometimes shrink Barrowgoyf. Unlicensed Hearse can also grow and eventually kill them.
Force of Will may be boarded out if you think they take out the combo completely, though I still like it as it can efficiently answer Dark Ritual + X on card parity.
Force of Negation is great against turbo and control, e.g. if you see Personal Tutor, Cabal Ritual, The One Ring, Teferi, Vexing Bauble(?).
Stifle works both against Fetchlands and against the Oracle trigger, so if you have it I would always keep it.
Consign to Memory 


Eco:

Vs Doomsday you should look for Personal Tutors, Cabal Rituals and 2nd green cycler+2nd Street Wraith.
If they have those, they are focused on Combo.
If they have creatures, you can trim a Wasteland and not bring in Consign. 

### Red Daze Decks

<mtg-card name="Dragon's Rage Channeler"/>
<mtg-card name="Lightning Bolt"/>
<mtg-card name="Daze"/>


Minyafriend:
> Be aware Stifle is a thing.
> In: blasts, removal, Goyfs Out: FoW, Thoughtseize

Eco:

Black Daze vs. Red Daze is a cool matchup where they fold to a lot of your cards.
Play the matchup some more, and you’ll win more games for sure.
Focus on stopping aggression and accepting Daze instead of falling behind too much.
Sometimes we can respect Daze, but if you respect it too much, you will get run over.
Build basics if possible.

#### Sideboarding

##### In
<mtg-card name="Hydroblast"/>
<mtg-card name="Blue Elemental Blast"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Sheldred's Edict"/>

##### Out

## RUG Druid
<mtg-card name="Delver of Secrets"/>
<mtg-card name="Questing Druid"/>

Before Cutter was printed this was the main red variation and a good matchup for UB as you can kill all their threats one-for-one and outvalue their Druids.
If you can kill an unflipped Delver or a non-delirious Dragon's Rage Channeler with Orcish Bowmaster you should be miles ahead, but that is easier said then done, so don't allin on that as you are already favored most of the time.
Barrowgoyf is extremely hard to handle for them.

Your Nihil Spellbomb timing is very important here:
If they have a delirious Dragon's Rage Channeler then using it in the attack step can be used to chump block it with a Nethergoyf or an Orc Army token.
However a resolved Murktide is often a huge problem for you and once it is in play the Spellbomb may even grow it, so you may have to use it earlier.
Taking away Delirium can also be useful to save your creatures from Unholy Heat.

### UR Cutter
<mtg-card name="Cori-Steel Cutter"/>
<mtg-card name="Mishra's Bauble"/>

Stopping the Cutter is a priority because it snowballs out of control quickly and if they get a second one they often one-shot you even from close to 20 life.
Beware of their combat tricks as they can get lots of prowess triggers and even give Murktide Regent haste by equipping the Cutter.
Engineered Explosives may be necessary to survive long enough to stabilize with a Barrowgoyf.
On the draw you may have to cut one Kaito and you also may need to keep in some Forces even though they are bad against Pyroblast because the Cutter is so deadly and produces multiple threats.

### Boros Energy (<1% Meta game)
<mtg-card name="Goblin Bombardement"/>
<mtg-card name="Guide of Souls"/>
<mtg-card name="Ajani, Nacatl Pariah"/>

#### Sideboarding
Grindy go-wide aggro deck that we are disadvantaged against without Toxic Deluge but with the current MTGO meta it is hard to justify that sideboard slot.
Still winnable without if you get an engine (Tamiyo, Barrowgoyf, Kaito) into play ahead of them, then you may be able to keep their board clean and outvalue them.

##### In
Barrowgoyf is the perfect creature for matchups like this but they also have a lot to deal with it like Swords to Plowshares and Static Prison, see if you can play around Galvanic Discharge at least.


* Barrowgoyf
* removal
* Engineered Explosives
* Hydroblast
* Toxic Deluge if you have it

##### Out

* Daze
* Nihil Spellbomb
* shave Wasteland

### Goblins (<1% Meta game)

<mtg-card name="Cavern of Souls"/>
<mtg-card name="Aether Vial"/>
<mtg-card name="Goblin Lackey"/>
<mtg-card name="Broadside Bombardiers"/>
<mtg-card name="Goblin Matron"/>
<mtg-card name="Muxus, Goblin Grandee"/>

If you see green-producing lands, they may be on Food Chain (rare), adapt accordingly with more countermagic.

Similar to Boros Energy in that they are a go-wide aggro strategy but their creatures are weaker individually and have better synergy, such as Lackey into Muxus.
Bring in in removal, Barrowgoyf and Blue Blasts, board wipes if you have them.
Board out Nihil Spellbomb and Daze, shave Wasteland.
If possible I would play around Blood Moon but not if it puts you too far behind as they don't always have it in the sideboard and may not bring it in.

### Cradle Control (1% Meta game)

### Example Decklist
Austrian Challenge @ Gamestore (Linz, Austria) 1st place by Simon Ritter 2025-06-21

* 2 Forest
* 2 Bayou
* 2 Windswept Heath
* 2 Wooded Foothills
* 2 Misty Rainforest
* 2 Verdant Catacombs
* 2 Dryad Arbor
* 4 Gaea's Cradle
* 1 Lair of the Hydra
* 2 Talon Gates of Madara
* 1 Bojuka Bog
* 4 Noble Hierarch
* 4 Ignoble Hierarch
* 1 Sylvan Safekeeper
* 4 Wight of the Reliquary
* 3 Keen-Eyed Curator
* 1 Collector Ouphe
* 1 Atraxa, Grand Unifier
* 4 Thoughtseize
* 4 Once Upon a Time
* 4 Green Sun's Zenith
* 3 Natural Order
* 1 Grist, the Hunger Tide
* 4 Elvish Reclaimer

#### Sideboard
* 4 Snuff Out
* 4 Endurance
* 1 Wasteland
* 1 Urza's Saga
* 1 Pithing Needle
* 3 Force of Vigor
* 1 Gaddock Teeg

A fair Green-Black creature deck with a lands subtheme, sometimes with Natural Order for Atraxa.
Like most fair non-blue creature decks, it is structurally advantaged against blue tempo decks.
It doesn’t require critical mass so they aren't stopped by Force of Will and they have mana dorks so they aren’t that impacted by Daze and Wasteland.
Still I would keep Force of Will in for tempo because you are disadvantaged in the late game.
It is hard to beat for Tempo without board wipes like Rough/Tumble due to their large number of creatures.

They have a slew of combat tricks that they are probably much more experienced with than you so think twice before blocking a seemingly stupid attack.
Putting any land from their library into play with Elvish Reclaimer and Wight of the Reliquary can do the following:

<mtg-card name="Bojuka Bog"/>
<mtg-card name="Elvish Reclaimer"/>
<mtg-card name="Wight of the Reliquary"/>
<mtg-card name="Gaea's Cradle"/>
<mtg-card name="Dryad Arbor"/>
<mtg-card name="Talon Gates of Madara"/>

* Bojuka Bog can shrink your Nethergoyf
* Lands in the graveyard grow Elvish Reclaimer.
* Creatures in the graveyard grow Fiend Artisan (rarely played) and and Wight of the Reliquary
* Gaea’s Cradle provides a burst of mana, e.g. for an Endurance
* Dryad Arbor can block.
* They may play Talon Gates of Madeira to phase out a creature but rarely.
* However they usually don’t play Dark Depths and Maze of Ith.

* They also have Orcish Bowmaster, Endurance and (Ig)noble Hierarch so think twice before exposing your seemingly safe Kaito.

On the positive side they can’t interact with countermagic outside of Veil of Summer.
Also they can’t block fliers outside of Endurance and Birds of Paradise (rarely played).

They usually seem to have enough mana so I board out some Dazes and often leave the mana dorks alone though it depends on the situation.
Orcish Bowmaster is nice even though they don’t draw many cards but you can kill (Ig)noble Hierarch, Birds of Paradise and so on.
Be careful not to confuse Wight and Knight: Wight sacrifices creatures and grows with them in the yard, Knight sacrifices plains or forests and grows with lands in the yard.
Grist is really confusing: You can’t Force of Negation it, Grafdigger’s Cage doesn’t stop it from coming into play, it grows Wight. But when it’s in play you can’t kill it with creature removal. Grist is very dangerous because if it gets going you never get any creatures into play and you lost the game.
At least you can hit it with Orcish Bowmasters, attack it with a flyer (if Grist doesn’t kill it, maybe a Brazen Borrower), but best to just counter it or the Green Sun’s Zenith for 3.
They play 4 Green Sun’s Zenith so it may be worth it to board in Grafdigger’s Cage so they can only get Grist and a GSZ for 4 mana you can hopefully Daze or Force at that time.
Due to the low play rate it’s not worth it to play sideboard hate specifically for them but there is some overlap like Toxic Deluge that is great vs Nadu as well.
Traditionally, Submerge is often played in tempo if you expect lots of green creature decks but with black removal not caring about the toughness of creatures, UB does rarely play it.
Hard graveyard hate like Surgical Extraction is not worth it due to it being card disadvantage but graveyard hate that can also be a threat is very useful to shrink their X of the Reliquary, for example Emperor of Bones or maybe Unlicensed Hearse or even Nihil Spellbomb.
You can block a big creature with Tamiyo and then brainstorm to flip it before damage. If they have Orcish Bowmasters their trigger goes on the stack first and Tamiyo flips first and fizzles the triggers.

### Maverick (<1%)
Similar to the creature part of Cradle Control with a single Cradle and a white splash for Swords to Plowshares and Knight of the Reliquary instead of or in addition to Wight of the Reliquary.
Hard to say exactly what they play as it is pretty rare so keep your eyes open for cards like Stoneforge Mystic, Thalia, Guardian of Thraben, Mother of Runes and maybe even the Dark Depth's Combo.

They play Wastelands so start with basics to keep from falling behind in tempo.
Additional tricks:
Lands in the graveyard grow Knight of the Reliquary (+2/+2 through a Fetchland)
Karakas can bounce a legendary creature such as Tamiyo.

Sideboarding: Similar to Cradle Control
* In: Barrowgoyf, Hearse, Submerge, Emperor of Bones, Orcish Bowmasters, all the spot and mass removal, e.g. Fell, Shoot the Sheriff, Go for the Throat, Sheoldred's Edict, Toxic Deluge, Threads of Disloyalty (they have enchantment removal though), Submerge.

*TODO: update*
With the example list I would -1 Wasteland -4 Daze -1 Nihil Spellbomb +1 Hearse +1 Barrowgoyf +1 Sheoldred’s Edict +1 Toxic Deluge +1 Long Goodbye +1 Brazen Borrower
Their Plan: Their plan is already good so they won’t change much, probably Collector Ouphe out and Choke in.

### Elves (<1%)

<mtg-card name="Heritage Druid"/>
<mtg-card name="Nettle Sentinel"/>
<mtg-card name="Glimpse of Nature"/>
<mtg-card name="Allosaurus Shepherd"/>
<mtg-card name="Gaea's Cradle"/>
<mtg-card name="Green Sun's Zenith"/>
<mtg-card name="Natural Order"/>
<mtg-card name="Atraxa, Grand Unifier"/>
<mtg-card name="Craterhoof Behemoth"/>

Marquee Legacy creature combo + value deck a long time ago that got powercrept out of the top decks over time, then Orcish Bowmasters caused most Elves players to switch to Cradle Control.
Their main Glimpse of Nature combo gets destroyed by Orcish Bowmasters so they probably board that out.
If go wide creature strategies ever become a significant factor in your meta you can crush them with 1-2 Toxic Deluge in your sideboard but the power level of UB tempo is so high that you can often win without any board wipes.
Still structurally advantaged against midrange and tempo due to them going wide, producing enough mana so Daze and Wasteland aren't as strong, having some tricks against removal and Allosaurus Shepherd turning off your countermagic.
Also if you aren't a long time Legacy player you probably lose a few games at first due to failling for their various tricks or misjudging which of their various plans they are trying to go for.

They have multiple plans though as a non-blue deck they can't always choose which one they go for, you should learn them to identify pressure points for your interaction:

### Glimpse Combo

<mtg-card name="Heritage Druid"/>
<mtg-card name="Birchlore Rangers"/>
<mtg-card name="Nettle Sentinel"/>
<mtg-card name="Glimpse of Nature"/>
<mtg-card name="Gaea's Cradle"/>

As they don't usually play Veil of Summer, Orcish Bowmasters destroys this combo.
If you don't have that, killing Heritage Druid often prevents them getting too much value.
You can also Force the Glimpse though that may be a bluff, for example if they already made their land drop to play around Daze and cannot threaten a Heritage Druid activation.
Daze on Glimpse can also be worth it if they are low on mana.

### Grind Mode

<mtg-card name="Allosaurus Shepherd"/>
<mtg-card name="Elvish Visionary"/>
<mtg-card name="Wirewood Symbiote"/>
<mtg-card name="Eladamri, Korvecdal"/>
<mtg-card name="Quirion Ranger"/>
<mtg-card name="Dryad Arbor"/>
<mtg-card name="Grist, the Hunger Tide"/>

They can nullify most of your interaction and try to accumulate value over time while stalling your ground offensive by bouncing Elves with Wirewood Symbiote and Dryad Arbor with Quirion Ranger.
A quick and large Murktide can often kill them before they accrue too much value.
Spot removal needs to kill Wirewood Symbiote first as it cannot bounce itself unless they make it an Elf (like Mirror Entity, which noone plays in Legacy anymore).

### Big Creature

<mtg-card name="Natural Order"/>
<mtg-card name="Atraxa, Grand Unifier"/>
<mtg-card name="Craterhoof Behemoth"/>
<mtg-card name="Allosaurus Shepherd"/>
<mtg-card name="Gaea's Cradle"/>
<mtg-card name="Eladamri, Korvecdal"/>

Whether you can FoW or FoN a Natural Order probably decides who will win or lose that game.
If they have an Allosaurus Shepherd, you can kill it while Natural Order is on the stack and then counter.
They can also just get enough mana to hardcast Craterhoof or sometimes even Atraxa using the colored mana from Birchlore Rangers.

#### Sideboarding


##### In
<mtg-card name="Toxic Deluge"/>
<mtg-card name="Engineered Explosives"/>
<mtg-card name="Sheoldred's Edict"/>
<mtg-card name="Grafdigger's Cage"/>
<mtg-card name="Force of Negation"/>

* any mass removal has extreme value
* any spot removal, even Sheoldred's Edict which often doesn't kill what you want but at least they can't use bounce tricks
* Cage stops both Green Sun's Zenith and Natural Order (except for Grist)

##### Out
<mtg-card name="Nihil Spellbomb"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Baleful Strix"/>
<mtg-card name="Daze"/>

Barrowgoyf is too easy for them to stall.
Even with Wasteland, Daze is hard to keep active on the draw due to Gaea's Cradle and Heritage Druid.
On the play you can also keep Daze in and not bring in FoN, especially if you have Cage.

##### Their Plan
<mtg-card name="Glimpse of Nature"/>
<mtg-card name="Endurance"/>
<mtg-card name="Keen-Eyed Curator"/>
<mtg-card name="Choke"/>
<mtg-card name="Abrupt Decay"/>

Due to Orcish Bowmasters they probably board out Glimpse of Nature and bring in Endurance and Keen-Eyed Curator to both handle your graveyard synergies and present threats that don't need synergy.
They may also bring in Choke so fetch a basic swamp if it doesn't hinder your game plan too much.
They may also board out some or all Dryad Arbor as I feel it is not as impactful.

### Mono Black Aggro (<1% Meta game)

<mtg-card name="Stalactite Stalker"/>
<mtg-card name="Nethergoyf"/>
<mtg-card name="Dauthi Voidwalker"/>
<mtg-card name="Hymn to Tourach"/>
<mtg-card name="Barrowgoyf"/>
<mtg-card name="Opposition Agent"/>
<mtg-card name="Dark Ritual"/>
<mtg-card name="Volrath's Stronghold"/>
<mtg-card name="Wasteland"/>

Grindy fair deck that aims to win a battle of attrition.
Even though Force is a two-for-one I would still keep it, sometimes you can protect an Engine like Tamiyo or Kaito long enough to outvalue them.
Be careful with fetching and brainstorming, they could Dark Ritual into Bowmaster and (postboard?) Opposition Agent.
Value-grave hate like Nihil Spellbomb is fine.
Can also have a small red splash for sideboard Pyroblast.

#### Sideboarding

<mtg-card name="Sheoldred's Edict"/>

##### In

* removal
* creatures

##### Out

* Daze

### Burn (<1% Meta game)
<mtg-card name="Lava Spike"/>
<mtg-card name="Goblin Guide"/>
<mtg-card name="Fireblast"/>
<mtg-card name="Monastery Swiftspear"/>
<mtg-card name="Eidolon of the Great Revel"/>

Good matchup if you have enough Barrowgoyfs.
Can also race with Nethergoyf.

#### Sideboarding

##### In

<mtg-card name="Barrowgoyf"/>
<mtg-card name="Hydroblast"/>
<mtg-card name="Force of Negation"/>
<mtg-card name="Flusterstorm"/>

Consign to Memory against Rift bolt may also be worth it and it pitches to Force.

##### Out

<mtg-card name="Thoughtseize"/>
<mtg-card name="Orcish Bowmasters"/>

You can also shave on Wasteland but Barrowgoyf T3 is important.

Their plan: 

They will bring in Pyroblast.
Sometimes they have Roiling Vortex or Ensnaring Bridge so I would keep a Brazen Borrower in if there isn't anything better.

<mtg-card name="Pyroblast"/>
<mtg-card name="Roiling Vortex"/>
<mtg-card name="Ensnaring Bridge"/>


### Pox (<1% Meta game)

<mtg-card name="Smallpox"/>
<mtg-card name="Liliana of the Veil"/>
<mtg-card name="Karn, the Great Creator"/>
<mtg-card name="Urza's Saga"/>
<mtg-card name="Leyline of the Void"/>

Ultra grindy creatureless matchup which you may win on the clock on MTGO if they go for Ensnaring Bridge, but in paper you have to play fast and be ready to call a judge to prevent slow play.
They have lots of creature removal but struggle with planeswalkers, so going for a quick Tamiyo ultimate may help.
Ensnaring Bridge is annoying but can sometimes be handled using creative thinking.
Besides preparing a lethal attack (take Sudden Edict into account) and then using Brazen Borrower, you can for example create Kaito emblems for a few turns and Ninjutsu it from a Tamiyo or use one of the many other ways you have to shrinking and growing your creatures before and after the attack.
As the deck is rarely played competitively expect lots of variations and adapt to what you see.

#### Sideboarding
##### In
* Barrowgoyf
* Brazen Borrower
* Sheoldred's Edict
* Force of Negation

##### Out
* Daze
* Fatal Push
* Orcish Bowmasters

### LED Dredge (<1% Meta game)

A unique graveyard deck that requires very specific answers to beat but you shouldn’t tune your sideboard in an open field because of the extremely low play rate.
Good matchup as long as you have enough grave hate. 2 mainboard Nihil Spellbombs really help.

Play carefully, focus on sideboard, mulligan, early turns. Don’t let spells through too quickly, think what you want to counter! E.g. against most other decks you often let LED resolve but here you should counter it.
Mulligan for grave hate, they are the beatdown. 
If you don’t have grave hate, stick early threats, counter their enabler (anything that discards cards) and try to kill them quickly.
Be careful with Thoughtseize if they are low on cards because you might win them the game by being forced to discard a dredger.

* In: All graveyard hate, FoN, BEB (Faithless Looting, Ox of Agonas), Counterbalance, 
Barrowgoyf, Submerge, Emperor of Bones, Orcish Bowmasters, all the spot and mass removal, e.g. Fell, Shoot the Sheriff, Go for the Throat, Sheoldred's Edict, Toxic Deluge, Threads of Disloyalty (they have enchantment removal though), Submerge.
* Out: Fatal Push, Orcish Bowmaster, 
* Their Plan: Win game 1 and hope to get one of the postboard games.


### Tempo Decks

*TODO: some disagree with that and keep Force in, update*
Always the first thought when I build a sideboard is that I want to have exactly as many cards to bring in as I want to bring out.
The easiest way to achieve that is number of Thoughtseize + Forces main = number of BEB + removal + creatures side (not counting Harbinger) 
The reason for the Thoughtseize-BEB switch is that DRC + Bolt kill you quickly.
It’s OK to have 1-2 FoW in your mapping isn’t perfect, can also board out 1 Daze and keep in 1 Force on the draw.
You have a great tempo matchup as you can remove almost anything, only Murktide, Counterbalance and Kaito can be difficult to handle. 

### Red Delver decks

*TODO: update (other people have other opinions on sideboarding)

The most aggressive variants, focus on survival first.
In: BEB, removal and creatures
Out: Thoughtseize, Force of Will


UB Delver/Tempo
In: Removal and creatures
Out: Force of Will
(% Meta game)


Quick Tips:
Assume UB Reanimator due to higher play rate until you see Nethergoyf, Kaito or main deck Nihil Spellbomb, most of the other cards are unfortunately shared between both decks.
Don’t forget about Kaito! For example you should always block Tamiyo if you can. It’s very hard to remove for UB except with combat damage, so get creatures on the board quickly.

## Disclaimers
1. I refer to "UB Tempo" because that name it is most used by the community but the deck has midrange elements.
2. Stay curious and improvise. Use those guidelines only as a starting point, and adapt to the situation at hand.
