# Hexchat-Google-Translator-Plugin


Download google_translator.py and trnaslate.py

Modify this lines on google_translator.py

```
default_from = 'en'
default_to = 'es'
```

Place google_translator.py and trnaslate.py in /home/user/.config/hexchat/addons to auto-load at hexchat startup.

mkdir if addons does not exist

# Usage


*note: Right clicking on channel or user will promt the menu and [+] or [-] autotranslate option will add them to watchlist, default from, to languages are used.*

Adding channels to the watch list for automatic translations.  If tar  get language is not specified, then the DEFAULT LANG set will be used. If source language is not specified, then language detection will be used.

```
/ADDTRC <channel> <target_language> <source_language>

# removing it from watchlist
/RMTRC <channel>
```

```
# For adding users
/ADDTR <user_nick> <target_language> <source_language>

# For removing users
/RMTR <user_nick>
```

Tracking watchlist

```
# list of channels
# format
# <network> <channel_name> => (<target_language>,<source_language>)
/LSCHANNELS

# list of users
/LSUSERS
```

For sending messages in target language to a users or in channel (already in watchlist) start the message with "!!"

```
# eg channel #testing is added to watchlist
/ADDTRC #testing de en

# since the target language is German
!!no
# will promt the message
# > no
# then sends the translated message to the channel 
nein
```

For translating the message when user or channel not in watchlist, starthe message with "@@" this will use the default source and target language. 

```
# default source is 'en' and target is 'es' (these lines can be modified in google_translator.py) 
@@yes
# promt output (only visible on user side)
Sí
```
# Additional Commands


```
# equivalent to starting the message with "@@"
/TR <message>
```
Translates message into the language according to form "to-from".  Thisauto detects the source language

```
/TRA <source language> <target language> <message>
```
Translates message into the language specified.  This auto detects the source language.'

```
/STR <message>
```
Sends a message translated according to form "to-from", where "from" isthe default language of origin and "to" is the default language destination

# Reloading Script 


Unload the google-translator.py script then reload the python module. 

Directly reloading google-tranlator.py script invokes multiple instances of translate module.

