# Changelog

## Version 1.0.6 (19 Sep 2023)

* Core: improved assets routing 

## Version 1.0.5 (18 Sep 2023)

* UI: Replace Rollbar with self-hosted GlitchTip to avoid sending potentially sensitive user data to 3rd party

## Version 1.0.4 (15 Sep 2023)

* Core: Added CORS headers for assets served over CDN

## Version 1.0.3 (14 Sep 2023)

* Core: upgrade to Rails 7.0
* UI: New frontend build pipeline with vite

⚠️ Security content

Multiple vulnerabilities was fixed by upstream dependencies:

* [CVE-2021-29509](https://nvd.nist.gov/vuln/detail/CVE-2021-29509)
* [CVE-2021-41136](https://nvd.nist.gov/vuln/detail/CVE-2021-41136)
* [CVE-2022-23634](https://nvd.nist.gov/vuln/detail/CVE-2022-23634)
* [CVE-2022-24790](https://nvd.nist.gov/vuln/detail/CVE-2022-24790)
* [CVE-2023-38037](https://nvd.nist.gov/vuln/detail/CVE-2023-38037)
* [CVE-2023-40175](https://nvd.nist.gov/vuln/detail/CVE-2023-40175)

Impact:

* **Affected** by Puma's Keep-alive Connections Denial Of Service
  * Users and their data **are not affected** by Denial Of Service attack
  
* Not affected by Puma's request smuggling attacks:
  * Only snippet routes are exposed: create, update and fork
  * Only snippet edits requests can be smuggled, but they required edit key, which is not stored in user session and attacker must obtain it beforehand
  * We have no indication that this attack was performed against Playground after 12 Sep 2023
  
* Not affected by Active Support encrypted files disclosure 
  * We don't store any files 

## Version 1.0.2 (13 Sep 2023)

* UI: Replace Rollbar with self-hosted GlitchTip to avoid sending any data to 3rd parties

## Version 1.0.1 (12 Sep 2023)

* UI: Replace Google Analytics with self-hosted Plausible to preserve your privacy in GDPR complaint way

## Version 1.0.0 (12 Sep 2023)

Playground is back 🥳

* Core: Update dependencies
* CI: Automatic deployments

## Version 0.6.4 (24 Jun 2020)

* Core: Allow identifier names (aka 'unqoted' strings) as keys
* Core: Show error message when ISODate is invalid
* UI: Resize data editor when split panel size changed

## Version 0.6.3 (23 Mar 2020)

* Core: Redirect back to snippet when edit key doesn't match
* Core: Show error message when collection failed to create

## Version 0.6.2 (19 Mar 2020)

* UI: Disallow `?edit=` in robots.txt
* CI: Report deploys to Rollbar

## Version 0.6.1 (19 Mar 2020)

* Core: MongoDB v4.2 compatibility
* Core: Temporary databases are cleaned even when command sequence is failed

## Version 0.6 (10 June 2019)

* Core: Allow non-ASCII symbols in strings
* Core: Show proper error message when query document is invalid

## Version 0.5 (12 Feb 2019)

* Core: Show error message when query or collections is empty string
* Core: Show error message when query failed to execute
* Core: Emit EJSON events and use them to react on state changes
* UI: Show confirmation dialog when leaving playground with unsaved changes
* UI: Allow running queries with a keyboard shortcut: Cmd/Ctrl+Enter
* UI: Highlight matching brackets
* UI: Reduce flickering on initial load in Chrome
* UI: Restore style of validation messages (was broken by 0.4.1)

## Version 0.4.1 (10 Feb 2019)

* UI: Update, Query & Aggregate Operator snippets are added
* UI: Aggregation snippets are loaded only in Aggregation playground

## Version 0.4.0 (8 Feb 2019)

* Core: Add Explain output for Find and Aggregate commands
* UI: Find And Modify editor now fully loads (was broken by 0.3.1)

## Version 0.3.1 (7 Feb 2019)

* Core: Fix issue with EJSON integration, that broke some playgrounds.

## Version 0.3 (7 Feb 2019)

* Core: FindAndModify and Update playgrounds added
* Core: Support all Mongo Extended JS(ON) features, including NumberDecimal. Thanks to [EJSON](https://github.com/db-ai/mongo-ejson) parser
* Core: Query & collection size limit increased to 32Kbyte
* UI: Editing experience improved by adding real-time syntax checker in the editor

## Version 0.2 (30 Jan 2019)

* Core: Find playground added
* Core: Snippets now can be forked
* UI: Unnecessary scrollbar removed from control panel

## Version 0.1 (22 Jan 2019)

* Core: Aggregation Pipeline playground added
