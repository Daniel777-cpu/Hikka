# Hikka Changelog

## 🌑 Hikka 1.4.2

- Fix authorization error

## 🌑 Hikka 1.4.1

- Create new type :obj:`hikka.tl_cache.CustomTelegramClient` to avoid monkeypatching
- Add `ttl` param for :method:`hikka.utils.asset_channel`
- Add support for custom branches (e.g. for beta testers and users, who rolled back)
- Fix automatic modules reactions
- Fix :method:`hikka.inline.utils.Utils._find_caller_sec_map`
- Fix the targeted security rules without time limit
- Require Hikka-TL >= 1.24.9
- Refactor `document_id` of custom emojis
- Refactor validators to be classes, not functions
- Refactor typehints

## 🌑 Hikka 1.4.0

- Publish hikka telethon fork and migrate to it in requirements, thereby fixing the deployment error on Heroku
- Add custom emojis filter to `utils.remove_html`
- Fix `client.get_perms_cached`
- Fix translation flaw in `HikkaSecurity`
- Fix `.uninstall_hikka` being accessible by sudo
- Fix `utils.find_caller` for :method:`hikka.inline.utils.Utils._find_caller_sec_map`
- Fix `.eval`
- Fix: use old lib if its version is higher than new one
- Fix grep for messages bigger than 4096 UTF-8 characters
- Add more animated emojis to modules
- Add targeted security for users and chats (`.tsec`)
- Add support for `tg_level` in `.config Tester`
- Add `-f` param to `.restart` and `.update`
- Add platform-specific Hikka emojis to premium users
- Add codepaces to `utils.get_named_platform`
- Add `Presets` core module
- Add handler for `/start` command in inlinebot with userbot info
- Rename `func` tag to `filter` due to internal python conflict with dynamically generated methods
- Partially rework security unit
- Internal refactoring and typehints
- Remove custom :obj:`BotInlineMessage` hook for :method:`answer`

## 🌑 Hikka 1.3.3

- Fix typo, which broke `client.get_fulluser`

## 🌑 Hikka 1.3.2

- Add `on_change` param to `loader.ConfigValue`
- Rework commands\inline handlers\callback handlers\watchers registration and unload process
- Rework tags processing
- Add junk collector aka reloader to `Modules`

## 🌑 Hikka 1.3.1

- Add caching to `utils.asset_channel`
- Add `channel` param to `utils.asset_channel` to actually create a channel, not supergroup
- Add watcher tags: `startswith`, `endswith`, `contains`, `regex`, `func`, `from_id`, `chat_id`
- Add buttons to `Choice` validator in `.config`
- Add new types: `PointerList`, `PointerDict`
- Add `db.pointer`
- Add `self.pointer` to module and library instances
- Add support for multiaccounting on Heroku
- Add ability to edit only reply markup or only media of message, w/o touching the actual text
- Add support for `@loader.command`-like commands in inline caller finder
- Add `utils.find_caller`
- Add possible cause of error in logs (module and method)
- Add `client.get_perms_cached` to cache native `client.get_permissions`
- Add `client.get_fullchannel` with cache
- Add `client.get_fulluser` with cache
- Add `exp` and `force` params to `client.get_perms_cached` and `client.get_entity`
- Add `exp` cached values check in `client.get_perms_cached` and `client.get_entity`
- Add text validation to info (automatically remove broken tags)
- Add `utils.validate_html` to remove broken tags from text
- Change errors format in web to more human-readable
- Change visible line of traceback in logs to be the last one
- Fix bug with custom_bot option on installation page
- Fix `RecursionError` in entity cacher
- Fix command execution with space between prefix and command
- Fix `utils.answer` for forwarded messages
- Remove `heroku3` from classic requirements, along with heroku installation code snippet
- Remove `termux_requirements.txt`
- Remove legacy `self.get` migration from strings
- Move `hikka._types` to `hikka.types` with legacy support
- Remake all core modules to decorators
- Force custom hikka telethon installation with 144 layer support
- Add animated emojis to core modules strings
- Add trigger to toggle the appearence of custom emojis

## 🌑 Hikka 1.3.0

- Patch stats so they correctly recognize links
- Fix bug when `...` is being replaced with `..` (unnecessary prefix escape)
- Add `@loader.tag`
- Add watcher tags: `no_commands`, `only_commands`, `out`, `in`, `only_messages`, `editable`, `no_media`, `only_media`, `only_photos`, `only_videos`, `only_audios`, `only_docs`, `only_stickers`, `only_inline`, `only_channels`, `only_groups`, `only_pm`. See docs for detailed info
- Add `utils.mime_type` to get mime_type of file in message
- Replace token obtainment mechanism with callback instead of inline
- Do not cut off prefix in `message.message`, `message.text` and `message.raw_text`
- Partially rework events processing and dispatching
- Attempt to fix cached entities mixing up
- Do not update modules in db when secure boot is active
- Refactor members getterr
- Add uptime to `.info`
- Refactor `.help`, add version to single mod help message
- Fix TypeError in `.e` when returning tl class instead of object
- Remove stupid db lock in `.e`
- Allow `.security` and `.inlinesec` only to owner by default
- Add support for `# requires` metatag in libraries
- Add support for `# scope: hikka_min` metatag in libraries
- Send stats of libraries, if enabled in `.settings`
- Replace library existence check from source url to classname
- Add `self.inline` to libraries
- Add `@loader.command`, `@loader.watcher`, `@loader.inline_handler`, `@loader.callback_handler`
- Add support for multiple watchers
- Add support for command translate directly in decorator (`@loader.command(ru_doc="Привет")`)
- Add support for :obj:`aiogram.types.Message` in `utils.get_chat_id`
- Add human-readable error message when trying to unload core module
- Replace `print` with `logging.info` in main script to make url visible in logs
- Automatically react to module post in developer's channel if possible

## 🌑 Hikka 1.2.12

- Automatically patch reply markup in inline form in the way, that edit stays available anyway
- Do not unload inline form automatically, keep it for 10 minutes instead
- Use `telethon.utils.resolve_inline_message_id` to remove inline unit
- Add `self.request_join`
- Allow developers to declare `client_ready` without arguments

## 🌑 Hikka 1.2.11

- Add support for lib attribute `version` (must be defined BEFORE `init` method)
- Add `self.lookup` to libs
- Add `self.allmodules` to libs
- Add `self._lib_get` to libs
- Add `self._lib_set` to libs
- Add `self.get_prefix` to libs
- Add `self.tg_id` to libs
- Add `client.tg_id` to every TelegramClient
- Add support for hook `on_lib_update` (invoked when library is being updated by new version)
- Add adequate library migration with references replacement
- Add support for markup, generated for messages, sent by bot itself
- Reformat code with `black --preview`
- Automatically send photo as gif if possible in form
- Update quickstart
- New fields in HikkaInfo
- Remove suffix `Hikka` if user specified it somewhere below
- New exception handler
- Fix back button in `.config <lib>`
- New `.e` error format
- Ignore folder creation error
- Fix unload error in module without commands
- Rework aiogram media processing on edit

## 🌑 Hikka 1.2.10

- Completely drop fast_uploader support
- Add :method:`utils.import_lib`
- Add protection for :obj:`CheckChatInviteRequest` in forbid_joins
- Add ability to search modules by classname in :method:`self.lookup`
- Add anonymous stats of modules loading (YOU CAN DISABLE THEM IN `.settings`)
- Add telethon objects formatting in `.e`
- Add :obj:`loader.SelfSuspend` to disable module commands and watcher loading, e.g. if library is unavailable
- Add migration native modules db storage from `strings["name"]` to classname. ⚠️ Might break some stuff in the beginning in rare cases
- Fix heroku-specific config error

## 🌑 Hikka 1.2.9

- Small patch which allows developer to specify audio metadata in form and `_edit_unit`

## 🌑 Hikka 1.2.8

- Add automatic webpage bot unblock in heroku waker
- Add secure boot feature
- Update native heroku postgre database saving method
- Add easter egg to `.ping`
- Add platform-specific errors while installing requirements
- Change postgresql column `id` datatype from int32 to int64 + legacy migration
- Change proxypass tunnel behavior - now it only opens on setup and via command `.weburl`
- Lavhost-specific web url
- Meaningful errors in web
- ⚠️ Drop `fast_uploader` support. It will be completely removed in next major update
- Deepsource fixes
- Multiple languages with priority

## 🌑 Hikka 1.2.7

- Add automatic proxy pass
- Fix --no-web argument parsing
- Fix localization error in updater
- Print out only INFO statements to stdout
- Add rotating file handler (logfile with max 10MB size)
- Show web endpoint on startup if available
- Fix gallery `inline_message_id` error
- Add support for `custom_buttons` in `inline.list`
- Add support for `custom_buttons` in `inline.gallery`
- Smart fast_uploader (Do not use hard download on files smaller than 1 MB)
- Attempt to parse `unit_id` from passed `InlineCall` object in `inline._delete_unit_message`
- Reformatting
- Change typehints
- Show list-like values in formatted way in config
- Properly escape html in config
- Split config to pages and categories (core \ non-core)
- Properly edit dictionary config (iter)
- Properly remove items from series options through built-in configurator
- Remove warning from web by replacing coroutine generation with `functools.partial`

## 🌑 Hikka 1.2.6

- Fix processing of `# scope: hikka_min`
- Add `forbid_joins.py` (to use it, download module from official repo with the same name)

## 🌑 Hikka 1.2.5

- Add additional exit on restart to avoid port block
- Add unloaded module name on `.unloadmod`
- Add `banner_url` config var to `HikkaInfo`
- Add `loader.validators.Hidden`
- Add `websockets` dependency, so users can load hikarichat on Heroku
- Add `reply_markup` kwarg to `utils.answer`. This will automatically add buttons to plain message or edit buttons of inline unit
- Add suggestion to join developer's channel on module load if available
- Add `client.force_get_entity` to bypass Hikka Cacher
- Add clickable link to loaded module message if specified meta developer is channel
- Add support of `action` attributes for buttons ("action": "close", "action": "unload", "action": "answer")
- Add log splitter between different clients of instance (if possible)
- Fix inline events `IndexError`
- Fix text in inline input
- Fix translation issue in HikkaConfig
- Fix `.dump`
- Fix modules list reset if you perform `.dlmod` when userbot is not yet fully loaded
- Update links in README
- Remove nalinor from official repos until new modules appear

## 🌑 Hikka 1.2.4

- Show current options in module config
- Add new validators: `loader.validators.Union`, `loader.validators.NoneType`
- Add additional Heroku deps
- Fix `load_module` reattempt
- Reorder database read-writes to make postgres the ladder
- Make redis optional for non-heroku users
- Add source to Pipfile
- New Heroku dependencies list in Pipfile
- External Redis database support
- Mask more options in logs and .e output
- Remove psycopg2 from requirements.txt
- New installation banner
- Add automatic blob->raw convertion in loader
- Add banner with Hikka installation status
- Reorder config saving in web
- Fix `Unauthorized` error on Heroku

## 🌑 Hikka 1.2.3

- Add field `action` to inline buttons. You can pass there `close` to close inline form, `unload` to unload it from memory, `answer` & `text` | `show_alert` to answer callback query with message
- Update docstrings in inline to match unified format
- Add surrogate error ignorance in dispatcher
- Fix :obj:`EntityCache` caching username `@None`
- Return :obj:`InlineMessage` in `hikka.inline.gallery.Gallery.gallery`
- Fix typo in docstring

## 🌑 Hikka 1.2.2

- Update gitignore so git doesn't count shit on heroku
- Visual heroku fixes in updater
- Deepsource fixes
- Add `utils.get_entity_url`, `utils.get_message_link`, `utils.remove_html`, `utils.get_kwargs`
- Disable modules debugging on heroku
- Add `.nonickusers`, `.nonickcmds`, `.nonickchats`
- Update blacklist command docs
- Fix grep removing everything in <...>
- Add `loader.validators.RegExp`
- Automatically convert `None` to empty string \ zero integer etc., if validator is specified
- More meaningful errors in `inline_handler`s
- More meaningful errors in `self.inline.form`, `self.inline.gallery`, `self.inline.list` on user-side
- Allow editing\adding media to form via `call.edit`. Currently supported: `photo`, `file`, `video`, `audio`, `gif`

## 🌑 Hikka 1.2.1

- Add termux specific requirements
- Refactor `heroku.py` app searching algorithm
- Refactor postgresql database saving process
- Fix heroku restart message not being edited
- Add heroku waker
- Make `hikka-` app naming optional

## 🌑 Hikka 1.2.0

- Add full-featured Heroku support with additional buildpacks
- Notify which dependencies are being installed in .dlmod
- Additional GeekTG compat layer
- Fix logging chat
- Rework sessions storage and retrieval
- Rework session processing in web

## 🌘 Patch released

- Allow adding and removing multiple items in config
- Add `ast.literal_eval` to config
- Add explicit typecheck for `mod.config`

## 🌑 Hikka 1.1.28

- Fix non-working param `share_link` in loader
- Assure logging bot is a member of logchat
- Do not store partial phone number in session, only ID
- Rework fast uploader so more types can be passed. For more information check code docstrings and typehints
- Rework installer so it properly displays which action is currently happening
- Fix `Series` not accepting one item
- Show upcoming commit in update and warn if update is not required
- Add reset to default button to config
- Merge `hikka_logger.py` with `test.py`
- Localization
- Allow opening options of specific mod via arguments in `.config`
- Add `add` and `remove` buttons to `Series` params
- Do not unload form immediately, if `ttl` param was passed explicitly

## 🌑 Hikka 1.1.27

- Reorder the steps of parsing in `loader.validators.Series`
- Fix aliases (yet another time)
- Fix minor bug in `loader.validators.Series`, which allowed to put empty string in it
- Fix some translation issues and type conversion ones
- Fix incorrect modules loading if multiple links end with specified name
- Fix type conversion bug in `loader.validators.String`
- Fix typehints flaws
- Add additional fields to `inline.form`: `gif`, `file`, `mime\_type`, `video`, `location`, `audio`
- Add reset-to-default action, if config is invalid while loading the userbot to prevent fall
- Add verification emoji to `input` to let user know, that new value was processed
- Add badge showing how much the last restart took
- Add `min_len`, `max_len`, `fixed_len` params to `loader.validators.Series`
- Add option to show downloaded module link in result message of `.dlmod`
- Add explicit database save after applying new config
- Add hint to web
- Add code of conduct
- Add changelog
- Remove redundant code in `database.py` as it literally does nothing

## 🌑 Hikka 1.1.26

- Hopefully finally fix aliases being reset after restart
- Remove redundant internal hook \_client\_ready2
- Show user evaluated version of config value instead of pre-comp one
- Add validator for each item to Series, remove separator
- Add new validator: TelegramID

## 🌑 Hikka 1.1.25

- Add separate messages on restart and full\_restart. Second one is shown, when all modules are loaded
- Replace .uninstall\_hikka with full uninstallation (remove bot, asset chats and folder)
- Suggest update if it is required by module
- New validator: Float
- Buttons in .config of option is a boolean value
- Drop support of argument positive in loader.validators.Integer as it can be easily replaced with minimum=0
- Update semantic generator in validators
- Yet another protection from monkey-patching

## 🌑 Hikka 1.1.24

- Add String and Link validators
- Fix Series validator
- Reformat core modules to use validators

## 🌑 Hikka 1.1.23

- Add config validators (loader.validators, Boolean, Integer, Choice, Series)
- Change info layout
- Add .uninstall\_hikka
- Add .clearlogs
- Refactor code
- Fix minor bugs
- Fix aliases being reset after restart (aliases will now be available only when userbot is fully loaded)

## 🌑 Hikka 1.1.22

- Fix bugs related to web, more specifically: Session save timing, adding more than 1 account and proper restart
- Rework Dockerfiles so they work properly
- Add uvloop so the asyncio runs faster
- Add Docker badge to info
- Improve Okteto performance by adjusting settings in okteto-stack.yml
- New ascii\_faces in utils
- Typehints update
- Fix Okteto pinger messages removal

## 🌑 Hikka 1.1.21

- Fix translation typos
- Add nonick suggestion when adding user to group
- Add entity caching

## 🌑 Hikka 1.1.20

- Add legacy fs modules migration
- Add ready asyncio Event to help track userbot loading process from outside
- Replace logging in loader with module-dependent one
- Fix some bugs and bug-risk issues
- Send big logs as file, rather than an infinite series of messages
- HTML-escape # meta developer:
- Make self.animate available for core modules and modules, loaded from file

## 🌑 Hikka 1.1.19

- Fix infinite loops
- Add client-specific check of fs modules
- Use classname of module, if it is possible to parse it with ast
- Rework infinite loops stopping and modules instance placement

## 🌑 Hikka 1.1.18

- Add notification about not exact match in help
- Add automatic progress bar generation to self.fast\_upload and self.fast\_download
- Make Mod ending in modules class name not mandatory

## 🌑 Hikka 1.1.17

- Fix some weird looking code
- Fix some emojies and translation issues
- Add native lavHost support (.restart, .update) via internal API
- Add utils.get\_lang\_flag()

## 🌑 Hikka 1.1.16

- Fix config docstrings and html escaping
- Fix typehints
- Fix some security staff
- Add additional bot username check
- Add additional foolchecks
- Migrate to walrus operator where necessary
- Remove redundant code block
- Add default aiogram parse mode
- Rename some core stuff which was not supposed to be used by external developers

## 🌑 Hikka 1.1.15

- Add automatic database autofix and rollback if database was broken by module
- Fix translation issues
- Warn user, if he tries to view .help when userbot is not yet fully loaded
- Create alias for \_generate\_markup (generate\_markup)
- Fix modules which are deleting from helphide
- Automatically save db if it was edited via classic dictionary methods

## 🌑 Hikka 1.1.14

- Fix utils.asset\_channel()'s archive param
- Fix defect, which forced installation from additional trusted repo, rather than from primary one if the file names are matched
- Add avatar to utils.asset\_channel() which automatically sets chat pic on creation (be careful, bc it leads to floodwaits, if you do it often)
- Add automatic hikka folder processing
- Add avatars to all official repo modules, which require asset chats (and add them to hikka folder)
- Rework database assets chat processing
- Replace some minor stuff like texts and emojies
- Force many core modules to use self.get\self.set rather than digging the db
- Add .fconfig command to forcefully set known config value if it doesn't fit in Telegram query
- Add dataclasses for module config (read the docs for more info), bc old way is blasphemy
- Automatically save config value if it was set to module self.config\[option\] = value
- Add utils.is\_serializable(), utils.set\_avatar()
- Send very large (over 4096\*10 symbols) output in a file rather than in an inline list

## 🌑 Hikka 1.1.13

- Fix processing commands on behalf of channel
- Fix .settings Restart and Update
- Add warning in call.edit(), if message was sent w\o buttons, ergo Telegram won't allow to edit this message
- Add --force restart
- Add ability to customize .info (this is only your problem, if you break something)
- Properly censor known tokens in logs
- Replace regex check in utils.check\_url() with urllib parser

## 🌑 Hikka 1.1.12

- Consider avoiding redundant requests to TG API in order to get the client id and rather using self.\_tg\_id, which is now available for all modules

## 🌑 Hikka 1.1.11

- Add fast uploader (self.fast\_upload, self.fast\_download)
- Fix translations

## 🌑 Hikka 1.1.10

- Add ability to download modules from many additional repos (e.g. you can download weather by morisummer via just .dlmod weather, and also list all available repos via .dlmod)

## 🌑 Hikka 1.1.9

- Fix \_generate\_markup in order that it automatically sets up callback hooks to \_custom\_map if callback was passed in buttons
- Add switch\_inline\_query and switch\_inline\_query\_current\_chat parsers
- Fix minor issues

## 🌑 Hikka 1.1.8

- Stuff, related to translation issues
- Add self.get\_prefix() to all modules, which returns current command prefix
- Add possibility to silently self-unload mod, e.g if some condition is not matched. Usecase can be found in modules/okteto.py
- Add async def on\_dlmod(self, client: "TelegramClient", db: "database.Database") handling. This can be e.g. used to subscribe to module's author's channel
- Rework Okteto Pinger, so it removes messages, if userbot is installed on other platform and so it even works
- Add trusted developers to quickstart message
- Automatically switch language via quickstart message button

## 🌑 Hikka 1.1.7

- Add self.animate function to all modules, which allows you to easily create fancy animations

## 🌑 Hikka 1.1.6

- Allow and process callback field in result of inline query answer. You can also use this in your own functions. Simply pass prepare\_callbacks=True to \_generate\_markup
- Generate InlineCall object on \_custom\_map handlers

## 🌑 Hikka 1.1.5

- Minor update: Allow passing disable\_security and always\_allow to buttons directly

## 🌑 Hikka 1.1.4

- Ability to set inline bot username on setup (in web interface)
- Fix inline help
- Add more debug info to logs
- Add attribute status to loops
- Fix HikkaDL link parsing
- Suggest enabling value in bounding mask if it is not
- Mask tokens in logs
- Add utils.get\_git\_hash()
- Add debugging mode for developers

## 🌑 Hikka 1.1.3

- Finally (hopefully) fix config
- Minor bug fixes related to inline form processing

## 🌑 Hikka 1.1.2

- Add @loader.loop, which provides developers access to easy-to-make infinite loops. Wait for developers docs to update for more info

## 🌑 Hikka 1.1.1

- Drop Uniborg and Raphielgang compatibility layer. More info in [2d525ab](https://github.com/hikariatama/Hikka/commit/2d525ab6b0e6b9d7ccd7408bbe175cea24d780a5)
- Minor bug fixes

## 🌑 Hikka 1.1.0

- Make inline commands' docstrings translatable
- Introducing HikkaDynamicTranslate - the possibility for developers to translate their own modules to other language without usage of native translates
- Rework translates system, because «translate channels wut¿». Now translate pack can be loaded from disk or from web
- Add utils.check\_url
- Get rid of babel
- Add IP address and possible cities to web auth popup
- Add web auth popup ratelimit
- Automatically delete web auth flow when timeout's exceeded
- Adapt core modules so they send plain text message, if unable to send inline
- New type: InlineMessage
- Rework type InlineCall
- Make it so the forms, lists and galleries return editable InlineMessage
- Return a single answerable value from utils.answer, not a list
- Ensure that inline unit is actually being unloaded
- Refactor inline - remove redundant arguments, rename some core methods
- Fix userbot crash when using galleries' slideshow for a long time
- Rework slideshow so it runs in the background
- Fix here, fix there, fix somewhere...

## 🌑 Hikka 1.0.29

- Add option to control inline and callback handlers' security via loader decorators, including brand new @loader.inline\_everyone
- Refactor HikkaSecurity, especially the bounding mask control

## 🌑 Hikka 1.0.28

- Add silent param to inline.form, inline.gallery, inline.list
- Add photo param to inline.form
- Add URL validator to inline.\_generate\_markup
- Ignore MessageIdInvalidError in .e

## 🌑 Hikka 1.0.27

Thankfully to @bsolute, now we have a cool smart\_split in utils. The messages are split without loosing formatting and emojies, preferably on line breakes / spaces.

## 🌑 Hikka 1.0.26

- Add utils.smart\_split which splits message in chunks of chunk\_size, keeping parse\_mode and entities in a right way (relocates 'em)
- If response of utils.answer is too big to be sent in one particular message, it will be split in chunks of 4096 and sent via inline.list

## 🌑 Hikka 1.0.25

- Add disable\_security to inline forms, lists and galleries

## 🌑 Hikka 1.0.24

- Okteto fixes (persistent uri, fix webpage)
- Add utils.dnd, which allows to mute and archive peer
- Security fixes for groups (not super\mega groups)
- Minor bug fixes

## 🌑 Hikka 1.0.23

- Add ability to disable HikkaDL natively
- Fix Updater so it works if you have troubles with inline mode

## 🌑 Hikka 1.0.22

Add HikkaDL module to use inline download buttons in verified channels

## 🌑 Hikka 1.0.21

A lot of stuff: web fixes, bug fixes, automatic seamless userbot restart when adding new account in web, replace emojies, add inline list feature, fix types name conflict and I don't remember other fixes, read code

## 🌑 Hikka 1.0.20

- Allow passing reply\_markup field to InlineQuery's result
- Refactor reply markup parser so it accepts more formats of inline markup

## 🌑 Hikka 1.0.19

- Allow developers to pass InlineQuery result via return operator in inline handlers. Read the docs for more info
- Move query\_gallery to a separate module

## 🌑 Hikka 1.0.18

- Add silent and archive params to utils.asset\_channel.
- Remake logging so it become native with `BotLogger`.
- Inject `BotLogger` analog directly

## 🌑 Hikka 1.0.17

- Add ability to set up inline commands' security map (only `owner`, `sudo`, `support` and `everyone`, because other permissions are inaccessible when processing inline query).
- Add database serializeability check to avoid JSON-serialization problems if unserializable object is being stored in db.
- Minor bugfixes

## 🌑 Hikka 1.0.16

- Full support of Okteto cloud deployment inculding persistent data storage (additional volume is created)
- Fix automatic waker for container

## 🌑 Hikka 1.0.15

- Add more errors to query aka query.e500()

## 🌑 Hikka 1.0.14

- Add gallery slideshow

## 🌑 Hikka 1.0.13

- Include command prefix in inline info.
- Fix --no-web.
- Suggest to save modules to filesystem

## 🌑 Hikka 1.0.12

- Optimize forms, galleries and custom\_map storage by ommiting keys with default values and dynamically generate them.
- Add feature to inherit command-caller permissions on form and gallery (crutchy).
- Minor improvements and bug fixes

## 🌑 Hikka 1.0.11

- Add inline.query\_gallery to add ability to call inline gallery via inline query.
- Add `e404` attribute to `InlineQuery`, which should be shown, that no results were found

## 🌑 Hikka 1.0.10

- Add feature to send gifs in inline galleries (gif param).
- Make argument `caption` of inline gallery not mandatory

## 🌑 Hikka 1.0.9

- Full inline structure rework.
- Split this madness into separate modules (`InlineUnit`s), which extend the main unit - `InlineManager`.
- Compatibility layer is not main priority.

## 🌑 Hikka 1.0.8

- Code refactoring
- Minor bug fixes
- Rewrite security

## 🌑 Hikka 1.0.7

- Massive inline galleries update, memoization, back button, preloading and other features.
- Fix some minor bugs, add `ascii_face` to utils

## 🌑 Hikka 1.0.6

- Add welcome message, triggered when userbot is installed

## 🌑 Hikka 1.0.5

- Add gallery memoization (ability to close gallery and scroll it back)

## 🌑 Hikka 1.0.4

- Add Okteto pinger, which will wake the pod up, when it goes to sleep

## 🌑 Hikka 1.0.3

- Fix a lot of stuff in web
- Add new features to web
- Merge root and initial\_root
- Remove trailing whitespaces

## 🌑 Hikka 1.0.2

- Full restructure of core code
- Refactor web
- Create new active bg

## 🌑 Hikka 1.0.1

- Drop heroku support
- Remove redundant code
- Remake badge
- Remake installer
