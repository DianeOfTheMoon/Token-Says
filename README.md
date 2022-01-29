![all versions](https://img.shields.io/github/downloads/napolitanod/Token-Says/total) 
![Latest Release Download Count](https://img.shields.io/github/downloads/napolitanod/Token-Says/latest/module.zip)
[![Forge Installs](https://img.shields.io/badge/dynamic/json?label=Forge%20Installs&query=package.installs&suffix=%25&url=https%3A%2F%2Fforge-vtt.com%2Fapi%2Fbazaar%2Fpackage%2Ftoken-says&colorB=4aa94a)](https://forge-vtt.com/bazaar#package=token-says)
[![Foundry Hub Endorsements](https://img.shields.io/endpoint?logoColor=white&url=https%3A%2F%2Fwww.foundryvtt-hub.com%2Fwp-json%2Fhubapi%2Fv1%2Fpackage%2Ftoken-says%2Fshield%2Fendorsements)](https://www.foundryvtt-hub.com/package/token-says/)


# Token Says
Bring some penache into your world. With Token Says, make tokens speak dialog and play audio based on in game actions. Use rolltables and playlists to randomize what tokens say. 

![Animation](https://user-images.githubusercontent.com/22696153/127725224-f9af308d-fcfb-4f2b-a090-f267348928c6.gif)

> Pesky goblins harrass an Azer as they attack. Uses 'Insults For A Lawful Good Character Using Vicious Mockery' rolltable from FVTT Community Tables module in order to randomize through 100 insults.

## Video Overview (somewhat dated, does not include recent features)
https://youtu.be/_CRPy2LVicY

## Why Use?
A halfling archer that says little quips whenever they score a hit with their shortbow. A samurai warrior that expresses various teachings with each katana strike. A lion that roars on occasional bites. All of these things are possible with Token Says.

Token Says sayings are fully customizable by the GM and are designed to be flexible to your needs. Alleviate some of the burden of being a GM and give your players access to edit their own character's phrases by linking a saying to a rollable table that they have permission to edit. Or, make it simple and link to an existing compendium's rollable table! Don't think that halfling archer would come up with a quip every time? No sweat! Set a likelihood for how often a token will say a particular saying and Token Says will only trigger that percent of the time.

## How it Works
The Token Says feature uses a set of Token Says sayings that you create for your world in order to auto generate chat messages, chat bubbles and audio sounds when specific tokens or actors do something. The token may say the same thing every time or it can be randomized using a playlist or rollable table. Other features include:
* Use of compendium data so that the rollable tables and playlists do not need to be in your world (though you can use your world's data too). KEEP IN MIND THAT PLAYING FROM A COMPENDIUM CAN BE SLOW.
* Sayings can be specific to a certain action (e.g. token performs an attack roll with a warhammer) or generic (e.g. token performs an ability check).
* Sayings can be any text or sound - it doesn't have to be actual talking. Explosions on attack or footsteps on movement are valid uses.
* Likelihood can be set so that the token doesn't always say something. For example, with a likelihood of 10 set for a token's initiative check, they will only say something on 10% of their initiative sayings.


## Token Says Sayings

![image](https://user-images.githubusercontent.com/22696153/132096482-8fb1b093-d27a-49b3-ae5c-3312413dd5cd.png)

Token Says sayings can be configured within the "Open Sayings" area of the Token Says game module settings. Sayings are tabbed by rollable table or audio. Here you can:
* Add: add a new saying by select + Add in the subheader of that tab
* Edit: update an existing saying by selecting the edit pencil icon for that saying
* Delete: delete a saying by selecting the trash beside that saying's name


## Configure a Saying
![tsmove](https://user-images.githubusercontent.com/22696153/149647075-77013fc2-9321-46e7-ae79-30ff242320a8.gif)

> A Haregon speaks on arrival and his friend responds to their arrival - these are two sayings, one is an action type of Token Movement End and the other is an action type of Reponds To with the responding to action type of Token Movement End.

Each saying is configured on a specific token or actor, based on name, for a given action and the saying is only hit when that token or actor performs the action. 
* **Title:** Name each saying . The name is what displays in the Configure Token Sayings list.
* **Token Name:** Name the token for which this saying applies. This is case sensitive and mind the spelling! **Accepts multiple token names.** These must be delimited using the delimiter that you have chosen in your Token Says settings (e.g. Goblin|Witch|Werewolf ).
* **Use Actor Name:** Checking this will determine if the saying triggers based on the name of the actor associated to the token (as opposed to using the token name). This is useful in situations where your tokens may have different names than the source actor.
* **Language:** (only available if Polyglot module is installed). Choose a language to output the chat text and bubble in. If the token does not speak this language then the saying will not generate.
* **Action Type:** Select from a list of available options for triggering actions that may invoke a saying. Some types are system-specific. 
  * Ability Check: triggers on ability check roll by the token.
  * Attack Roll: triggers on attack roll by the token.
  * Condition/Effect Added: triggers when the condition or effect is added or toggled on for the token.
  * Condition/Effect Removed: triggers when the condition or effect is removed or toggled off for the token.
  * Damage Roll: triggers on damage roll by the token.
  * Initiative Roll: triggers on initiative roll by the token.
  * Item Name: triggers on roll of the item by the token (use this also for items that don't directly attack, such as items the invoke via saving throw in dnd)
  * Macro (API): triggers by a macro. see the API section below for details on how this is used.
  * Responds to: triggered by another token's action. Introduces a new form section where you specify an action that this saying is responding to. 
  * Saving Throw: triggered by a saving throw roll by the token.
  * Skill: triggered by a skill roll by the token.
  * Token Movement Start: triggered at the start of a token's move. The chat bubble will display at the token's start position. Audio will play at movement start.
  * Token Movement End: triggered at the end of a token's move. The chat bubble will display at the token's arrival position. Audio will play at movement end.
  * Turn in Combat: triggered at start of the token's turn in combat.
* **Action Name:** Type in the name of the action associated to the action type. **Accepts multiple action names.** These must be delimited using the delimiter that you have chosen in your Token Says settings (e.g. Sword|Staff|Wand ).
  * Ability Check (dnd5e): select ability
  * Attack Roll (dnd5e, pf2e): use the item name making the attack (e.g. Longbow)
  * Condition/Effect Added: use the name of the condition or effect that triggers the saying when it is added or toggled on for the token.
  * Condition/Effect Removed: use the name of the condition or effect that triggers the saying when it is removed or toggled off for the token.
  * Damage Roll (dnd5e, pf2e): use the item name making the damage roll (e.g. Longbow)
  * Initiative Roll: leave blank
  * Item Name: use the item name that triggers the saying when it is rolled (e.g. Action Surge)
  * Macro (API): see the API section below for details on how this is used
  * Responds to: leave blank (see the response section that is made visible and complete the Action Type and Action Name there)
  * Saving Throw (dnd5e): select ability
  * Skill (dnd5e, pf2e): select or enter skill
  * Token Movement Start: list the scenes where this saying can play (using the Scene Name). Leave blank to play on all scenes.
  * Token Movement End: list the scenes where this saying can play (using the Scene Name). Leave blank to play on all scenes.
  * Turn in Combat: leave blank
* **Token Says:** Use this to bypass randomization. Type in here what the token will say. For audio files, this is the name of the file to play for the given playlist or, if no playlist is included, this is the actual path to the audio file.
* **Playlist Name/Rollable Table Name:** The name of the rollable table or playlist. This can be left blank for rollable table sayings if you have entered something in the 'Token Says' field.
* **Compendium:** choose the compendium from which the roll table or playlist will be found. Note that this overrides your default compendium set in your Token Says settings. If you have selected in your settings to search your world's playlists or rollable tables first, those will be searched before going to this compendium. This can be left blank for rollable table sayings if you have entered something in the 'Token Says' field.
* **Delay:** add a time, in milliseconds, to wait between the generating action and the saying. Note that delays due to accessing compendium content and rolling on compendiums may add to this delay.
* **Volume:** Set the volume for this saying.
* **Only While Moving:** This toggle is available for the Action Type of Token Movement Start for audio sayings. The sound will play from the time when the token begins movement up to the time when the token stops movement. Useful for things like audible footsteps.
* **Likelihood:** Set on a scale of 1 to 100 what percent of the time the token will say something for this given saying. For example, a 33 for a likelihood that triggers on initiave rolls will cause the token to say something 33% of the time when they roll initiative.
* **Responds To:** this section is made visible if the 'Responds to' Action Name is selected
  * **Action Type:** the type of action that this saying responds to. Has the same set of options as the 'Action Type' within this saying's 'Provoking action' section, accept 'Responds to' is not an option while 'Saying' is. 
  * **Action Name:** similar to 'Action Name' in the 'Provoking Action' section, but for the action this saying is responding to.
  * **Token Name:** the name of the token that this saying is responding to. **Accepts multiple token names.** These must be delimited using the delimiter that you have chosen in your Token Says settings (e.g. Goblin|Witch|Werewolf ).
  * **Use Actor Name:** similar to the setting in the 'Provoking Action' section, but for the token that this saying is responding to.
  * **Only If In Sight:** requires the token to be able to see the token that they are responding to. Based on center-point calculation. Walls block.
  * **Distance:** token must be within this distance from the token that they are responding to. Consider this comparable to the distance within which they can hear the other token.
    * If responding to movement, distance is calculated from start of token position for 'Token Movement Start' and ending token position for 'Token Movement End'. Both are useful - in the former you may want to insult people who are retreating. In the latter you may want to let a person sneaking by know that you can see them.
* **Suppress Chat Bubble:** check this to prevent a chat bubble from generating for this saying.
* **Suppress Chat Message:** check this to prevent a chat message from generating for this saying.
* **Suppress Quotes:** check this to prevent the chat message from being wrapped in quotes "".

## Game Module Settings
See wiki https://github.com/napolitanod/Token-Says/wiki/Game-Module-Settings

## Token Form Access
Token Says sayings can be accessed from the header of either the token form or the prototype token form. This gives the GM immediate access from the token form to add, edit, or make other saying changes.
![image](https://user-images.githubusercontent.com/22696153/127880868-c95c4abe-c3e2-4b7e-9e19-de6be2fa9000.png)


## Export Your Token Sayings
Your sayings can be easily exported from the Token Says sayings configuration window using the export button to the right of the search bar.

## Import Token Saying and Share Between Worlds
Your sayings, or sayings from others, can be imported into your world. Imports add new sayings and do not delete existing sayings. Any saying in the import file that shares an id with a saying in your world will be skipped. Note that some sayings may need further configuration after import if compendiums or modules differ between your worlds.

## API / Macro Use

### .says() - call a specific saying from macro/script
The tokenSays.says(tokenId, actorId, actionName) function is made available for use within you macros and scripts. The function generates a Token Says message if a saying is found that matches the parameters that you pass in. The return from this function is the Token Says saying data for the saying identified by this function. 

To use this function you must have Token Says installed as a module and active and must have a saying with action type = "Macro (API)" with an Token Name that matches the alias of the token or name of the actor that you pass into the function as well as an Action Name that matches the actionName passed into the function.
* tokenId (optional) - the token.id. Though optional, either this or actor must be passed in, else the function will be escaped
* actorId (optional) - the actor.id. Can be derived from token if not provided.
* actionName - this must match to your Token Says saying "Action Name" for the given actor or token.
  * If the Action Name on a saying with Action Type = Macro (API) is left blank then that saying will trigger for that actor/token regardless of the actionName set here in the macro. 

![klhkg](https://user-images.githubusercontent.com/22696153/145907653-97f3c8de-8ac2-40bc-aea6-30967499de9a.png)
> An example saying set up to trigger an audio saying via macro. Note that the macro code is 2 lines. In the first line it grabs a token id by using the current token controlled by the user triggering the macro.


### .saysDirect() - use Token Says functionality without a saying in place
The tokenSays.saysDirect(tokenId, actorId, sceneId, options) function is available to module developers and Foundry users. The function generates a Token Says message based on the parameters. No existing sayings are referenced. This allows module developers and macro writers to dynamically have a token speak, giving them full control over the trigger. The return from this function is the Token Says workflow class that generated the saying.

To use this function you must have Token Says installed 
* tokenId (optional) - the token.id. Though optional, either this or actor must be passed in, else the function will be escaped
* actorId (optional) - the actor.id. Can be derived from token if not provided.
* sceneId (optional) - the scene.id. If not provided, the scene id for the current scene will be used
* options - dictates the rolltable or playlist that will be sourced as well as any compendium or likelihood data. This is an object, so each key below is wrapped in the same object. e.g. const options = { type: "rollTable",source: "Possession"}
  * type (required) - either rollTable or audio. Identifies if this is a playlist or rollable table.
  * source (optional) - the name of the rolltable or playlist. if not set for rolltable, then quote is required.
  * compendium (optional) - the compendium holding the playlist or rolltable. If not set, then the default Token Says compendium will be use or the world, depending on the Token Says settings of the world.
  * quote (optional) - the direct text said or the audio track in the playlist.
  * likelihood (optional) - as integer. The % of the time this will actually result in a Token Says message. if not provided, the default is 100.

## System Compatibility
This module has been tested in DND5e. Though my intent is to have it be system agnostic in terms of the basic features, there may be some incompatible systems that I am not aware of. The list of known compatible systems are:
* DND5e (developer confirmed)
* PF1 (developer confirmed)
* PF2e (developer confirmed)

#### Not compatible with
* L5R (this module does not include flavor in message data)

## Module Compatibility
* Midi-Qol: Token Says supports Midi-Qol functionality (tested in DND5e only)
* Polyglot: Token Says integrates with Polyglot in order to translate the token's speech using the current option in the chat message area. Both chat bubbles and chat message are transformed by polyglot.

## Note To Developers
* The flag of `flags: {TOKENSAYS: {cancel: true}}` within the chatMessage.Create() options can be used to escape out of Token Says. Add this flag to prevent Token Says from generating a chat message off of a specific message that you may create.
* Token Says uses Developer Mode Module for console.log output. By enabling Token Says through Developer Mode Debug you can gain access to the key events generated by Token Says workflow.

## Enhancements
See a list of upcoming enhancements on the project board https://github.com/napolitanod/Token-Says/projects/1

## Acknowledgements
* Thank you to Calego for their walkthrough on Foundry VTT module building (https://hackmd.io/@akrigline/ByHFgUZ6u/%2FNBub2oFIT6yeh4NlOGTVFw), this helped me quickly pick up the  basics. 
* If you use Monk's Enhanced Journal you'll see that the layout on one of my forms shares inspiration (and some CSS) from his ironmonk's module (https://github.com/ironmonk88)
* Thank you to everybody in the League of Extraordinary Developers Discord for their assistance in answering questions and troubleshooting

