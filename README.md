# Freak Fortress 2: Custom Attribute Adapter

This plugin allows Freak Fortress bosses to have custom attributes applied to their weapons via existing configuration files.

Works with spawn-in weapons (specified with weaponX) and weapons received at any point in the game (for example with rages).

**Runtime dependencies:**
1. [Freak Fortress 2](https://forums.alliedmods.net/forumdisplay.php?f=154) - Official/forked versions work equally well.
2. [TF2Items](https://github.com/asherkin/TF2Items). Please note that this plugin relies on *TF2Items_OnGiveNamedItem_Post*, which may not be included in the "Release" version of TF2Items. Make sure to grab a forked version of compile it yourself.
3. [Custom Attributes Framework](https://github.com/nosoop/SM-TFCustAttr)

**Installation:**

1. Install the [Custom Attributes Framework](https://github.com/nosoop/SM-TFCustAttr) following it's guide.
2. Install Freak Fortress 2 if you haven't already. There aren't any specific dependencies except FF2_GetBossKV, but it's available basically in every sensible FF2 version.
3. Compile this plugin and place it to addons/sourcemod/plugins/.
4. Install your desired Custom Attributes. Use ones from the [Public Custom Attribute Sets](https://github.com/nosoop/SM-TFCustAttr/wiki/Public-Custom-Attribute-Sets) page or write your own. The API is very simple and shouldn't be hard to understand, given that you know the basics of SourcePawn.

**Usage:**
Go to your boss' configuration file (usually at /addons/sourcemod/configs/freak_fortress_2/).
Add the following structure inside the "characters" section (where you add weapons, abilities, sounds and everything else):

```
  "Custom Attributes"
	{
		"Weapon Definition Index"
		{
			"custom attribute" "value"
		}
	}
```
Weapon Definition Index corresponds to the weapon definition index that you want to apply the attribute(s) to. It can be a weapon that the boss spawns with (weaponX) or a weapon that the boss gets during the round from it's abilities. Inside the section is a list of all custom attributes you wish to apply. Add as many Indexes and Attributes as you want.

**Debug:**
This plugin does not usually indicate it's activity in any way, but if you want to see it applying attributes, please turn on the **ff2_debug** convar on (provided by Freak Fortress 2).
