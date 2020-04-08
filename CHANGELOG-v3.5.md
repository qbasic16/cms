# Running Release Notes for Craft CMS 3.5

### Added
- Added the “Show rounded icons” user preference. ([#5518](https://github.com/craftcms/cms/issues/5518))
- Added the “Use shapes to represent statuses” user preference. ([#3293](https://github.com/craftcms/cms/issues/3293))
- Added the “Suspend by default” user registration setting. ([#5830](https://github.com/craftcms/cms/issues/5830))
- Added the ability to disable sites on the front end. ([#3005](https://github.com/craftcms/cms/issues/3005))
- Soft-deleted elements now have a “Delete permanently” element action. ([#4420](https://github.com/craftcms/cms/issues/4420))
- It’s now possible to set a custom route that handles Set Password requests. ([#5722](https://github.com/craftcms/cms/issues/5722))
- Field labels now reveal their handles when the <kbd>Option</kbd>/<kbd>ALT</kbd> key is pressed. ([#5833](https://github.com/craftcms/cms/issues/5833))
- Added the `brokenImagePath` config setting. ([#5877](https://github.com/craftcms/cms/issues/5877))
- Added the `siteToken` config setting.
- Added the `install/check` command. ([#5810](https://github.com/craftcms/cms/issues/5810))
- Added the `plugin/install`, `plugin/uninstall`, `plugin/enable`, and `plugin/disable` commands. ([#5817](https://github.com/craftcms/cms/issues/5817))
- Added the `|explodeClass` Twig filter, which converts class names into an array.
- Added the `|explodeStyle` Twig filter, which converts CSS styles into an array of property/value pairs.
- Added the `|push` Twig filter, which returns a new array with one or more items appended to it.
- Added the `|unshift` Twig filter, which returns a new array with one or more items prepended to it.
- Added the `raw()` Twig function, which wraps the given string in a `Twig\Markup` object to prevent it from getting HTML-encoded.
- Added support for the `CRAFT_CP` PHP constant. ([#5122](https://github.com/craftcms/cms/issues/5122))
- Added the `drafts`, `draftOf`, `draftId`, `draftCreator`, `revisions`, `revisionOf`, `revisionId` and `revisionCreator` arguments to element queries using GraphQL API. ([#5580](https://github.com/craftcms/cms/issues/5580)) 
- Added the `isDraft`, `isRevision`, `sourceId`, `sourceUid`, and `isUnsavedDraft` fields to elements when using GraphPQL API. ([#5580](https://github.com/craftcms/cms/issues/5580))
- Added the `assetCount`, `categoryCount`, `entryCount`, `tagCount`, and `userCount` queries for fetching the element counts to the GraphPQL API. ([#4847](https://github.com/craftcms/cms/issues/4847))
- Added the `locale` argument to the `formatDateTime` GraphQL directive. ([#5593](https://github.com/craftcms/cms/issues/5593))
- Added support for specifying a transform on assets’ `width` and `height` fields via GraphQL.
- Added `craft\base\ElementInterface::getIconUrl()`.
- Added `craft\config\GeneralConfig::getTestToEmailAddress()`.
- Added `craft\console\controllers\MailerController::$to`.
- Added `craft\controllers\AppController::actionBrokenImage()`.
- Added `craft\elements\actions\Delete::$hard`.
- Added `craft\elements\Asset::getSrcset()`. ([#5774](https://github.com/craftcms/cms/issues/5774))
- Added `craft\gql\ElementQueryConditionBuilder`.
- Added `craft\helpers\Assets::parseSrcsetSize()`.
- Added `craft\helpers\Assets::scaledDimensions()`.
- Added `craft\helpers\FileHelper::addFilesToZip()`.
- Added `craft\helpers\FileHelper::zip()`.
- Added `craft\helpers\Html::explodeClass()`.
- Added `craft\helpers\Html::explodeStyle()`.
- Added `craft\helpers\MailerHelper::normalizeEmails()`.
- Added `craft\helpers\MailerHelper::settingsReport()`.
- Added `craft\helpers\Queue`.
- Added `craft\models\Site::$enabled`.
- Added `craft\web\AssetBundle\ContentWindowAsset`.
- Added `craft\web\AssetBundle\IframeResizerAsset`.
- Added `craft\web\Request::getAcceptsImage()`.
- Added `craft\web\Request::getFullUri()`.
- Added the `_includes/forms/password.html` control panel template.
- Added the [iFrame Resizer](http://davidjbradshaw.github.io/iframe-resizer/) library.

### Changed
- User registration forms in the control panel now give users the option to send an activation email, even if email verification isn’t required. ([#5836](https://github.com/craftcms/cms/issues/5836)) 
- Activation emails are now sent automatically on public registration if the `deferPublicRegistrationPassword` config setting is enabled, even if email verification isn’t required. ([#5836](https://github.com/craftcms/cms/issues/5836))
- Large asset thumbnails now use the same aspect ratio as the source image. ([#5515](https://github.com/craftcms/cms/issues/5515))
- Preview frames now maintain their scroll position across refreshes, even for cross-origin preview targets.
- Preview targets that aren’t directly rendered by Craft must now include `lib/iframe-resizer-cw/iframeResizer.contentWindow.js` in order to maintain scroll position across refreshes.
- The preview frame header no longer hides the top 54px of the preview frame when it’s scrolled all the way to the top. ([#5547](https://github.com/craftcms/cms/issues/5547))
- Modal backdrops no longer blur the page content. ([#5651](https://github.com/craftcms/cms/issues/5651))
- Improved the styling of password inputs in the control panel.
- Improved the wording of the meta info displayed in entry revision menus. ([#5889](https://github.com/craftcms/cms/issues/5889))
- Plain Text fields are now sortable in the control panel. ([#5819](https://github.com/craftcms/cms/issues/5819))
- Database backups created by the Database Backup utility are now saved as zip files. ([#5822](https://github.com/craftcms/cms/issues/5822))
- It’s now possible to specify aliases when eager-loading elements via the `with` param. ([#5793](https://github.com/craftcms/cms/issues/5793)) 
- The `cpTrigger` config setting can now be set to `null`. ([#5122](https://github.com/craftcms/cms/issues/5122))
- The `pathParam` config setting can now be set to `null`. ([#5676](https://github.com/craftcms/cms/issues/5676))
- If the `baseCpUrl` config setting is set, Craft will no longer treat any other base URLs as control panel requests, even if they contain the correct trigger segment. ([#5860](https://github.com/craftcms/cms/issues/5860))  
- The `mailer/test` command now only supports testing the current email settings.
- Reference tags can now provide a fallback value to be used if the reference can’t be resolved. ([#5589](https://github.com/craftcms/cms/issues/5589))
- The `withTransforms` asset query param can now include `srcset`-style sizes (e.g. `100w` or `2x`), following a normal transform definition.
- The `QueryArgument` GraphQL type now also allows boolean values.
- Improved transform eager-loading support when using GraphQL API.
- `craft\db\ActiveRecord` now unsets any empty primary key values when saving new records, to avoid a SQL error on PostgreSQL. ([#5814](https://github.com/craftcms/cms/pull/5814))
- `craft\elements\Asset::getImg()` now has a `$sizes` argument. ([#5774](https://github.com/craftcms/cms/issues/5774))
- `craft\i18n\Formatter::asTimestamp()` now has a `$withPreposition` argument.
- `craft\services\Sites::getAllSiteIds()`, `getSiteByUid()`, `getAllSites()`, `getSitesByGroupId()`, `getSiteById()`, and `getSiteByHandle()` now have `$withDisabled` arguments.
- Improved `data`/`aria` tag normalization via `craft\helpers\Html::parseTagAttributes()` and `normalizeTagAttributes()`.
- Control panel form input macros and templates that accept a `class` variable can now pass it as an array of class names.

### Deprecated
- Deprecated `craft\gql\base\Resolver::extractEagerLoadCondition()` in favor of the new `ElementQueryConditionBuilder` class.
- Deprecated the `install/plugin` command. The new `plugin/install` command should be used instead.

### Removed
- Removed the [Interactive Shell Extension for Yii 2](https://github.com/yiisoft/yii2-shell), as it’s now a dev dependency of the `craftcms/craft` project instead. ([#5783](https://github.com/craftcms/cms/issues/5783))
- Removed `craft\controllers\UtilitiesController::actionDbBackupPerformAction()`.

### Fixed
- Fixed a bug where the `mailer/test` command wasn’t factoring in custom `mailer` configurations in its settings report. ([#5763](https://github.com/craftcms/cms/issues/5763))
- Fixed a bug where some characters were getting double-encoded in Assets fields’ “Default Upload Location”/“Upload Location” setting. ([#5885](https://github.com/craftcms/cms/issues/5885))
- Fixed a bug where `users/set-password` and `users/verify-email` requests weren’t responding with JSON when requested, if an invalid verification code was passed. ([#5210](https://github.com/craftcms/cms/issues/5210))

### Security
- The `_includes/forms/checkbox.html`, `checkboxGroup.html`, and `checkboxSelect.html` control panel templates now HTML-encode checkbox labels by default, preventing possible XSS vulnerabilities. If HTML code was desired, it must be passed through the new `raw()` function first.