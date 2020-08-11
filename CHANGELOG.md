# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

## [16.1.0](https://www.github.com/Mike111177/yargs-parser/compare/v7.0.0...v16.1.0) (2020-08-11)


### ⚠ BREAKING CHANGES

* adds support for ESM and Deno (#295)
* **ts:** projects using `@types/yargs-parser` may see variations in type definitions.
* drops Node 6. begin following Node.js LTS schedule (#278)
* the narg count is now enforced when parsing arrays.
* this reverts parsing behavior of booleans to that of yargs@14
* objects used during parsing are now created with a null
* populate error if incompatible narg/count or array/count options are used (#191)
* moving to c8 for coverage and dropping Node 6 from build matrix (#209)
* rework `collect-unknown-options` into `unknown-options-as-args`, providing more comprehensive functionality
* unless "parse-numbers" is set to "false", arrays of numeric strings are now parsed as numbers, rather than strings.
* we have dropped the broken "defaulted" functionality; we would like to revisit adding this in the future.
* maybeCoerceNumber now takes precedence over coerce return value (#182)
* options with leading '+' or '0' now parse as strings
* a flag with no right-hand value no longer populates defaulted options with `undefined`.
* quotes and beginning and endings of strings are not removed during parsing.
* drops Node 4 support
* the argv object is now populated differently (correctly) when hyphens and dot notation are used in conjunction.
* `boolean` flags defined without a `default` value will now behave like other option type and won't be set in the parsed results when the user doesn't set the corresponding CLI arg.
* arguments of form --foo, -abc, will no longer be consumed by nargs
* strings that fail `Number.isSafeInteger()` are no longer coerced into numbers.

### Features

* add `set-placeholder-key` configuration ([#123](https://www.github.com/Mike111177/yargs-parser/issues/123)) ([19386ee](https://www.github.com/Mike111177/yargs-parser/commit/19386eec911ba8819dcfc00894eb05a590f8ca37))
* add `strip-aliased` and `strip-dashed` configuration options. ([#172](https://www.github.com/Mike111177/yargs-parser/issues/172)) ([a3936aa](https://www.github.com/Mike111177/yargs-parser/commit/a3936aa21e89b9a7e4f3bc05d3e56c1eff6a6a79))
* add configuration option to "collect-unknown-options" ([#181](https://www.github.com/Mike111177/yargs-parser/issues/181)) ([7909cc4](https://www.github.com/Mike111177/yargs-parser/commit/7909cc4679c76770d4d7950ecd527da823b08f91))
* add halt-at-non-option configuration option ([#130](https://www.github.com/Mike111177/yargs-parser/issues/130)) ([a849fce](https://www.github.com/Mike111177/yargs-parser/commit/a849fce0ba37414b3f3c2e01a547654dc1035623))
* adds support for ESM and Deno ([#295](https://www.github.com/Mike111177/yargs-parser/issues/295)) ([195bc4a](https://www.github.com/Mike111177/yargs-parser/commit/195bc4a7f20c2a8f8e33fbb6ba96ef6e9a0120a1))
* allow configuration of prefix for boolean negation ([#94](https://www.github.com/Mike111177/yargs-parser/issues/94)) ([00bde7d](https://www.github.com/Mike111177/yargs-parser/commit/00bde7d60c433c188f2529a33bab187d40645f7d))
* also add camelCase array options ([#125](https://www.github.com/Mike111177/yargs-parser/issues/125)) ([08c0117](https://www.github.com/Mike111177/yargs-parser/commit/08c011796f83e84fe50ffb066a87ae2effadfc75))
* array.type can now be provided, supporting coercion ([#132](https://www.github.com/Mike111177/yargs-parser/issues/132)) ([4b8cfce](https://www.github.com/Mike111177/yargs-parser/commit/4b8cfce511edce5fe6f3c5a6d7eb147b56cd8f52))
* boolean arguments will not be collected into an implicit array ([#236](https://www.github.com/Mike111177/yargs-parser/issues/236)) ([34c4e19](https://www.github.com/Mike111177/yargs-parser/commit/34c4e19bae4e7af63e3cb6fa654a97ed476e5eb5))
* default value is now used if no right-hand value provided for numbers/strings ([#156](https://www.github.com/Mike111177/yargs-parser/issues/156)) ([5a7c46a](https://www.github.com/Mike111177/yargs-parser/commit/5a7c46a0c707fbd975150352619a0e90c42df227))
* expose camelCase and decamelize helpers ([#296](https://www.github.com/Mike111177/yargs-parser/issues/296)) ([39154ce](https://www.github.com/Mike111177/yargs-parser/commit/39154ceb5bdcf76b5f59a9219b34cedb79b67f26))
* **deps:** update to latest camelcase/decamelize ([#281](https://www.github.com/Mike111177/yargs-parser/issues/281)) ([8931ab0](https://www.github.com/Mike111177/yargs-parser/commit/8931ab08f686cc55286f33a95a83537da2be5516))
* don't coerce number from string with leading '0' or '+' ([#158](https://www.github.com/Mike111177/yargs-parser/issues/158)) ([18d0fd5](https://www.github.com/Mike111177/yargs-parser/commit/18d0fd582996b3004bc92f2b46b9cd9776550414))
* introduce greedy-arrays config, for specifying whether arrays consume multiple positionals ([#249](https://www.github.com/Mike111177/yargs-parser/issues/249)) ([60e880a](https://www.github.com/Mike111177/yargs-parser/commit/60e880a837046314d89fa4725f923837fd33a9eb))
* introduce nargs-eats-options config option ([#246](https://www.github.com/Mike111177/yargs-parser/issues/246)) ([d50822a](https://www.github.com/Mike111177/yargs-parser/commit/d50822ac10e1b05f2e9643671ca131ac251b6732))
* introduce single-digit boolean aliases ([#255](https://www.github.com/Mike111177/yargs-parser/issues/255)) ([9c60265](https://www.github.com/Mike111177/yargs-parser/commit/9c60265fd7a03cb98e6df3e32c8c5e7508d9f56f))
* make combining arrays a configurable option ([#111](https://www.github.com/Mike111177/yargs-parser/issues/111)) ([c8bf536](https://www.github.com/Mike111177/yargs-parser/commit/c8bf5365aa79876ca4f0f7e7d769e2b1a9aab73b))
* maybeCoerceNumber() now takes into account arrays ([#187](https://www.github.com/Mike111177/yargs-parser/issues/187)) ([31c204b](https://www.github.com/Mike111177/yargs-parser/commit/31c204b35eb35e9a3c382f8068e7cb80674a2f22))
* merge array from arguments with array from config ([#83](https://www.github.com/Mike111177/yargs-parser/issues/83)) ([806ddd6](https://www.github.com/Mike111177/yargs-parser/commit/806ddd6cacacb728e42828113e75c6700ffe4366))
* NaN can now be provided as a value for nargs, indicating "at least" one value is expected for array ([#251](https://www.github.com/Mike111177/yargs-parser/issues/251)) ([9db4be8](https://www.github.com/Mike111177/yargs-parser/commit/9db4be81417a2c7097128db34d86fe70ef4af70c))
* narg arguments no longer consume flag arguments ([#114](https://www.github.com/Mike111177/yargs-parser/issues/114)) ([60bb9b3](https://www.github.com/Mike111177/yargs-parser/commit/60bb9b3ec2809b7b0bec2c0de9e2078d1b3f8fdb))
* options that have had their default value used are now tracked ([#211](https://www.github.com/Mike111177/yargs-parser/issues/211)) ([a525234](https://www.github.com/Mike111177/yargs-parser/commit/a525234558c847deedd73f8792e0a3b77b26e2c0))
* populate error if incompatible narg/count or array/count options are used ([#191](https://www.github.com/Mike111177/yargs-parser/issues/191)) ([84a401f](https://www.github.com/Mike111177/yargs-parser/commit/84a401f0fa3095e0a19661670d1570d0c3b9d3c9))
* rework `collect-unknown-options` into `unknown-options-as-args`, providing more comprehensive functionality ([ef771ca](https://www.github.com/Mike111177/yargs-parser/commit/ef771ca6fa344e7cd30de5828b16ae965eddb409))
* reworking how numbers are parsed ([#104](https://www.github.com/Mike111177/yargs-parser/issues/104)) ([fba00eb](https://www.github.com/Mike111177/yargs-parser/commit/fba00ebfa77a097dd7d6bbf420bba8ba3a941436))
* support boolean which do not consume next argument. ([#171](https://www.github.com/Mike111177/yargs-parser/issues/171)) ([0ae7fcb](https://www.github.com/Mike111177/yargs-parser/commit/0ae7fcbc528bc7630b713b7e09b7a3a6b5fced9c))


### Bug Fixes

* **build:** push tag created for deno ([2186a14](https://www.github.com/Mike111177/yargs-parser/commit/2186a14989749887d56189867602e39e6679f8b0))
* boolean numeric short option ([#294](https://www.github.com/Mike111177/yargs-parser/issues/294)) ([f600082](https://www.github.com/Mike111177/yargs-parser/commit/f600082c959e092076caf420bbbc9d7a231e2418))
* raise permission error for Deno if config load fails ([#298](https://www.github.com/Mike111177/yargs-parser/issues/298)) ([1174e2b](https://www.github.com/Mike111177/yargs-parser/commit/1174e2b3f0c845a1cd64e14ffc3703e730567a84))
* **array, nargs:** support -o=--value and --option=--value format ([#262](https://www.github.com/Mike111177/yargs-parser/issues/262)) ([41d3f81](https://www.github.com/Mike111177/yargs-parser/commit/41d3f8139e116706b28de9b0de3433feb08d2f13))
* **deps:** update dependency decamelize to v3 ([#274](https://www.github.com/Mike111177/yargs-parser/issues/274)) ([4d98698](https://www.github.com/Mike111177/yargs-parser/commit/4d98698bc6767e84ec54a0842908191739be73b7))
* **setArg:** options using camel-case and dot-notation populated twice ([#268](https://www.github.com/Mike111177/yargs-parser/issues/268)) ([f7e15b9](https://www.github.com/Mike111177/yargs-parser/commit/f7e15b9800900b9856acac1a830a5f35847be73e))
* **types:** switch back to using Partial types ([#293](https://www.github.com/Mike111177/yargs-parser/issues/293)) ([bdc80ba](https://www.github.com/Mike111177/yargs-parser/commit/bdc80ba59fa13bc3025ce0a85e8bad9f9da24ea7))
* __proto__ will now be replaced with ___proto___ in parse ([#258](https://www.github.com/Mike111177/yargs-parser/issues/258)) ([63810ca](https://www.github.com/Mike111177/yargs-parser/commit/63810ca1ae1a24b08293a4d971e70e058c7a41e2))
* address bugs with "uknown-options-as-args" ([bc023e3](https://www.github.com/Mike111177/yargs-parser/commit/bc023e3b13e20a118353f9507d1c999bf388a346))
* address issue with array options with array default values ([#206](https://www.github.com/Mike111177/yargs-parser/issues/206)) ([f5f9e5a](https://www.github.com/Mike111177/yargs-parser/commit/f5f9e5a7ea91821f7c95e8eb4c71dc74de1bc907))
* allow null config values ([#108](https://www.github.com/Mike111177/yargs-parser/issues/108)) ([d8b14f9](https://www.github.com/Mike111177/yargs-parser/commit/d8b14f94e7ab4228c54370c183ef265824b41287))
* array should take precedence over nargs, but enforce nargs ([#243](https://www.github.com/Mike111177/yargs-parser/issues/243)) ([4cbc188](https://www.github.com/Mike111177/yargs-parser/commit/4cbc188b7abb2249529a19c090338debdad2fe6c))
* better handling of quoted strings ([#153](https://www.github.com/Mike111177/yargs-parser/issues/153)) ([2fb71b2](https://www.github.com/Mike111177/yargs-parser/commit/2fb71b2b1d25316f94786a385616ebe34a6cbd73))
* boolean arrays with default values ([#185](https://www.github.com/Mike111177/yargs-parser/issues/185)) ([7d42572](https://www.github.com/Mike111177/yargs-parser/commit/7d42572acf7e81f1d78f357b3229d415abe3d6c5))
* boolean now behaves the same as other array types ([#184](https://www.github.com/Mike111177/yargs-parser/issues/184)) ([17ca3bd](https://www.github.com/Mike111177/yargs-parser/commit/17ca3bdaada25605ab06fe72946d2da4b52087fa))
* convert values to strings when tokenizing ([#167](https://www.github.com/Mike111177/yargs-parser/issues/167)) ([57b7883](https://www.github.com/Mike111177/yargs-parser/commit/57b788303e1119ba5260b273e486b73d0d638ad8))
* do not set boolean flags if not defined in `argv` ([#119](https://www.github.com/Mike111177/yargs-parser/issues/119)) ([f6e6599](https://www.github.com/Mike111177/yargs-parser/commit/f6e65994a07cddbd3526052877aee4b307925f9d))
* eatNargs() for 'opt.narg === 0' and boolean typed options ([#188](https://www.github.com/Mike111177/yargs-parser/issues/188)) ([c5a1db0](https://www.github.com/Mike111177/yargs-parser/commit/c5a1db06eabc4dd249adf2a471156bd133b693bf))
* ensure consistent parsing of dot-notation arguments ([#102](https://www.github.com/Mike111177/yargs-parser/issues/102)) ([c9bd79c](https://www.github.com/Mike111177/yargs-parser/commit/c9bd79c657dabedb21b1cacf4c3f86b41180d24b))
* ensure empty string is added into argv._ ([#140](https://www.github.com/Mike111177/yargs-parser/issues/140)) ([79cda98](https://www.github.com/Mike111177/yargs-parser/commit/79cda989595a7da4a9fd3f39120da5001f68899c))
* flatten-duplicate-arrays:false for more than 2 arrays ([#128](https://www.github.com/Mike111177/yargs-parser/issues/128)) ([2bc395f](https://www.github.com/Mike111177/yargs-parser/commit/2bc395fb28300222e7c93c2682eb37311065198f))
* handling of one char alias ([#139](https://www.github.com/Mike111177/yargs-parser/issues/139)) ([ee56e31](https://www.github.com/Mike111177/yargs-parser/commit/ee56e3116800824b2b0d6a749950fb7eaac296ff))
* hyphenated flags combined with dot notation broke parsing ([#131](https://www.github.com/Mike111177/yargs-parser/issues/131)) ([dc788da](https://www.github.com/Mike111177/yargs-parser/commit/dc788daac7845f5cf7a44c2f73c84087441264ef))
* Ignore multiple spaces between arguments. ([#100](https://www.github.com/Mike111177/yargs-parser/issues/100)) ([d137227](https://www.github.com/Mike111177/yargs-parser/commit/d1372279d3fc574ecc67bf9b3a21d785dd33a5a4))
* implement [@antoniom](https://www.github.com/antoniom)'s fix for camel-case expansion ([3087e1d](https://www.github.com/Mike111177/yargs-parser/commit/3087e1d65e2448a230a9b3187c23eabc24829267))
* make requiresArg work in conjunction with arrays ([#136](https://www.github.com/Mike111177/yargs-parser/issues/136)) ([77ae1d4](https://www.github.com/Mike111177/yargs-parser/commit/77ae1d4e1c2590eeca025952671fff935ab7e884))
* maybeCoerceNumber now takes precedence over coerce return value ([#182](https://www.github.com/Mike111177/yargs-parser/issues/182)) ([2f26436](https://www.github.com/Mike111177/yargs-parser/commit/2f2643602f6310078c6ec141bd395435818f90ef))
* nargs should allow duplicates when duplicate-arguments-array=false ([#164](https://www.github.com/Mike111177/yargs-parser/issues/164)) ([47ccb0b](https://www.github.com/Mike111177/yargs-parser/commit/47ccb0b7fcca1b989ef97bb084e4aa2aaf2a7666))
* nargs was consuming too many arguments ([4fef206](https://www.github.com/Mike111177/yargs-parser/commit/4fef20615ab0a14627a9f8004f81d4baafe4b9f4))
* nargs was still aggressively consuming too many arguments ([9b28aad](https://www.github.com/Mike111177/yargs-parser/commit/9b28aad9c44d73e966d406c00218f004d31411e0))
* normalized keys were not enumerable ([#247](https://www.github.com/Mike111177/yargs-parser/issues/247)) ([57119f9](https://www.github.com/Mike111177/yargs-parser/commit/57119f9f17cf27499bd95e61c2f72d18314f11ba))
* only run coercion functions once, despite aliases. ([#76](https://www.github.com/Mike111177/yargs-parser/issues/76)) ([#103](https://www.github.com/Mike111177/yargs-parser/issues/103)) ([507aaef](https://www.github.com/Mike111177/yargs-parser/commit/507aaefac5f5d8ef0e8b121be4afe1c63b5bb0b8))
* scientific notation circumvented bounds check ([#110](https://www.github.com/Mike111177/yargs-parser/issues/110)) ([3571f57](https://www.github.com/Mike111177/yargs-parser/commit/3571f57af42036ee7b9734178b114a75c5a75762))
* should populate "_" when given config with "short-option-groups" false ([#179](https://www.github.com/Mike111177/yargs-parser/issues/179)) ([6055974](https://www.github.com/Mike111177/yargs-parser/commit/6055974a23b1a5fb8769eff433e7dd122cefba79))
* support keys that collide with object prototypes ([#234](https://www.github.com/Mike111177/yargs-parser/issues/234)) ([1587b6d](https://www.github.com/Mike111177/yargs-parser/commit/1587b6d91db853a9109f1be6b209077993fee4de))
* support negative numbers with decimal places ([#208](https://www.github.com/Mike111177/yargs-parser/issues/208)) ([850bbda](https://www.github.com/Mike111177/yargs-parser/commit/850bbdafcf8a4998f374dfce993422855d10716d))
* take into account aliases when appending arrays from config object ([#199](https://www.github.com/Mike111177/yargs-parser/issues/199)) ([f8a2d3f](https://www.github.com/Mike111177/yargs-parser/commit/f8a2d3f26a84cc57e210deb1aa27b580e4b06388))
* tokenizer should ignore spaces at the beginning of the argString ([#106](https://www.github.com/Mike111177/yargs-parser/issues/106)) ([f34ead9](https://www.github.com/Mike111177/yargs-parser/commit/f34ead9986476c94199f6bd843c394169bf67319))
* unknown options terminated with digits now handled by unknown-options-as-args ([#238](https://www.github.com/Mike111177/yargs-parser/issues/238)) ([d36cdfa](https://www.github.com/Mike111177/yargs-parser/commit/d36cdfa854254d7c7e0fe1d583818332ac46c2a5))
* **unknown-options-as-args:** '--' is not an unknown option ([#207](https://www.github.com/Mike111177/yargs-parser/issues/207)) ([3fee2d8](https://www.github.com/Mike111177/yargs-parser/commit/3fee2d895e9da14af978bbd1c7c9c20170c3aa59))


### Reverts

* make requiresArg work in conjunction with arrays ([#136](https://www.github.com/Mike111177/yargs-parser/issues/136)) ([f4a3063](https://www.github.com/Mike111177/yargs-parser/commit/f4a3063b17c4d921bb1e9551e23d32c9fb7c68b5))
* revert 16.0.0 CHANGELOG entry ([920320a](https://www.github.com/Mike111177/yargs-parser/commit/920320ad9861bbfd58eda39221ae211540fc1daf))


### Miscellaneous Chores

* update dependencies ([6dc42a1](https://www.github.com/Mike111177/yargs-parser/commit/6dc42a190a97a779ac01b6ddf3d405bddefb0e96))


### Build System

* drops Node 6. begin following Node.js LTS schedule ([#278](https://www.github.com/Mike111177/yargs-parser/issues/278)) ([9014ed7](https://www.github.com/Mike111177/yargs-parser/commit/9014ed722a32768b96b829e65a31705db5c1458a))
* moving to c8 for coverage and dropping Node 6 from build matrix ([#209](https://www.github.com/Mike111177/yargs-parser/issues/209)) ([f3a9316](https://www.github.com/Mike111177/yargs-parser/commit/f3a9316e470b0cc5c01981c9614ee935835d719b))


### Code Refactoring

* **ts:** move index.js to TypeScript ([#292](https://www.github.com/Mike111177/yargs-parser/issues/292)) ([f78d2b9](https://www.github.com/Mike111177/yargs-parser/commit/f78d2b97567ac4828624406e420b4047c710b789))

### [19.0.1](https://www.github.com/yargs/yargs-parser/compare/v19.0.0...v19.0.1) (2020-08-09)


### Bug Fixes

* **build:** push tag created for deno ([2186a14](https://www.github.com/yargs/yargs-parser/commit/2186a14989749887d56189867602e39e6679f8b0))

## [19.0.0](https://www.github.com/yargs/yargs-parser/compare/v18.1.3...v19.0.0) (2020-08-09)


### ⚠ BREAKING CHANGES

* adds support for ESM and Deno (#295)
* **ts:** projects using `@types/yargs-parser` may see variations in type definitions.
* drops Node 6. begin following Node.js LTS schedule (#278)

### Features

* adds support for ESM and Deno ([#295](https://www.github.com/yargs/yargs-parser/issues/295)) ([195bc4a](https://www.github.com/yargs/yargs-parser/commit/195bc4a7f20c2a8f8e33fbb6ba96ef6e9a0120a1))
* expose camelCase and decamelize helpers ([#296](https://www.github.com/yargs/yargs-parser/issues/296)) ([39154ce](https://www.github.com/yargs/yargs-parser/commit/39154ceb5bdcf76b5f59a9219b34cedb79b67f26))
* **deps:** update to latest camelcase/decamelize ([#281](https://www.github.com/yargs/yargs-parser/issues/281)) ([8931ab0](https://www.github.com/yargs/yargs-parser/commit/8931ab08f686cc55286f33a95a83537da2be5516))


### Bug Fixes

* boolean numeric short option ([#294](https://www.github.com/yargs/yargs-parser/issues/294)) ([f600082](https://www.github.com/yargs/yargs-parser/commit/f600082c959e092076caf420bbbc9d7a231e2418))
* raise permission error for Deno if config load fails ([#298](https://www.github.com/yargs/yargs-parser/issues/298)) ([1174e2b](https://www.github.com/yargs/yargs-parser/commit/1174e2b3f0c845a1cd64e14ffc3703e730567a84))
* **deps:** update dependency decamelize to v3 ([#274](https://www.github.com/yargs/yargs-parser/issues/274)) ([4d98698](https://www.github.com/yargs/yargs-parser/commit/4d98698bc6767e84ec54a0842908191739be73b7))
* **types:** switch back to using Partial types ([#293](https://www.github.com/yargs/yargs-parser/issues/293)) ([bdc80ba](https://www.github.com/yargs/yargs-parser/commit/bdc80ba59fa13bc3025ce0a85e8bad9f9da24ea7))


### Build System

* drops Node 6. begin following Node.js LTS schedule ([#278](https://www.github.com/yargs/yargs-parser/issues/278)) ([9014ed7](https://www.github.com/yargs/yargs-parser/commit/9014ed722a32768b96b829e65a31705db5c1458a))


### Code Refactoring

* **ts:** move index.js to TypeScript ([#292](https://www.github.com/yargs/yargs-parser/issues/292)) ([f78d2b9](https://www.github.com/yargs/yargs-parser/commit/f78d2b97567ac4828624406e420b4047c710b789))

### [18.1.3](https://www.github.com/yargs/yargs-parser/compare/v18.1.2...v18.1.3) (2020-04-16)


### Bug Fixes

* **setArg:** options using camel-case and dot-notation populated twice ([#268](https://www.github.com/yargs/yargs-parser/issues/268)) ([f7e15b9](https://www.github.com/yargs/yargs-parser/commit/f7e15b9800900b9856acac1a830a5f35847be73e))

### [18.1.2](https://www.github.com/yargs/yargs-parser/compare/v18.1.1...v18.1.2) (2020-03-26)


### Bug Fixes

* **array, nargs:** support -o=--value and --option=--value format ([#262](https://www.github.com/yargs/yargs-parser/issues/262)) ([41d3f81](https://www.github.com/yargs/yargs-parser/commit/41d3f8139e116706b28de9b0de3433feb08d2f13))

### [18.1.1](https://www.github.com/yargs/yargs-parser/compare/v18.1.0...v18.1.1) (2020-03-16)


### Bug Fixes

* \_\_proto\_\_ will now be replaced with \_\_\_proto\_\_\_ in parse ([#258](https://www.github.com/yargs/yargs-parser/issues/258)), patching a potential 
prototype pollution vulnerability. This was reported by the Snyk Security Research Team.([63810ca](https://www.github.com/yargs/yargs-parser/commit/63810ca1ae1a24b08293a4d971e70e058c7a41e2))

## [18.1.0](https://www.github.com/yargs/yargs-parser/compare/v18.0.0...v18.1.0) (2020-03-07)


### Features

* introduce single-digit boolean aliases ([#255](https://www.github.com/yargs/yargs-parser/issues/255)) ([9c60265](https://www.github.com/yargs/yargs-parser/commit/9c60265fd7a03cb98e6df3e32c8c5e7508d9f56f))

## [18.0.0](https://www.github.com/yargs/yargs-parser/compare/v17.1.0...v18.0.0) (2020-03-02)


### ⚠ BREAKING CHANGES

* the narg count is now enforced when parsing arrays.

### Features

* NaN can now be provided as a value for nargs, indicating "at least" one value is expected for array ([#251](https://www.github.com/yargs/yargs-parser/issues/251)) ([9db4be8](https://www.github.com/yargs/yargs-parser/commit/9db4be81417a2c7097128db34d86fe70ef4af70c))

## [17.1.0](https://www.github.com/yargs/yargs-parser/compare/v17.0.1...v17.1.0) (2020-03-01)


### Features

* introduce greedy-arrays config, for specifying whether arrays consume multiple positionals ([#249](https://www.github.com/yargs/yargs-parser/issues/249)) ([60e880a](https://www.github.com/yargs/yargs-parser/commit/60e880a837046314d89fa4725f923837fd33a9eb))

### [17.0.1](https://www.github.com/yargs/yargs-parser/compare/v17.0.0...v17.0.1) (2020-02-29)


### Bug Fixes

* normalized keys were not enumerable ([#247](https://www.github.com/yargs/yargs-parser/issues/247)) ([57119f9](https://www.github.com/yargs/yargs-parser/commit/57119f9f17cf27499bd95e61c2f72d18314f11ba))

## [17.0.0](https://www.github.com/yargs/yargs-parser/compare/v16.1.0...v17.0.0) (2020-02-10)


### ⚠ BREAKING CHANGES

* this reverts parsing behavior of booleans to that of yargs@14
* objects used during parsing are now created with a null
prototype. There may be some scenarios where this change in behavior
leaks externally.

### Features

* boolean arguments will not be collected into an implicit array ([#236](https://www.github.com/yargs/yargs-parser/issues/236)) ([34c4e19](https://www.github.com/yargs/yargs-parser/commit/34c4e19bae4e7af63e3cb6fa654a97ed476e5eb5))
* introduce nargs-eats-options config option ([#246](https://www.github.com/yargs/yargs-parser/issues/246)) ([d50822a](https://www.github.com/yargs/yargs-parser/commit/d50822ac10e1b05f2e9643671ca131ac251b6732))


### Bug Fixes

* address bugs with "uknown-options-as-args" ([bc023e3](https://www.github.com/yargs/yargs-parser/commit/bc023e3b13e20a118353f9507d1c999bf388a346))
* array should take precedence over nargs, but enforce nargs ([#243](https://www.github.com/yargs/yargs-parser/issues/243)) ([4cbc188](https://www.github.com/yargs/yargs-parser/commit/4cbc188b7abb2249529a19c090338debdad2fe6c))
* support keys that collide with object prototypes ([#234](https://www.github.com/yargs/yargs-parser/issues/234)) ([1587b6d](https://www.github.com/yargs/yargs-parser/commit/1587b6d91db853a9109f1be6b209077993fee4de))
* unknown options terminated with digits now handled by unknown-options-as-args ([#238](https://www.github.com/yargs/yargs-parser/issues/238)) ([d36cdfa](https://www.github.com/yargs/yargs-parser/commit/d36cdfa854254d7c7e0fe1d583818332ac46c2a5))

## [16.1.0](https://www.github.com/yargs/yargs-parser/compare/v16.0.0...v16.1.0) (2019-11-01)


### ⚠ BREAKING CHANGES

* populate error if incompatible narg/count or array/count options are used (#191)

### Features

* options that have had their default value used are now tracked ([#211](https://www.github.com/yargs/yargs-parser/issues/211)) ([a525234](https://www.github.com/yargs/yargs-parser/commit/a525234558c847deedd73f8792e0a3b77b26e2c0))
* populate error if incompatible narg/count or array/count options are used ([#191](https://www.github.com/yargs/yargs-parser/issues/191)) ([84a401f](https://www.github.com/yargs/yargs-parser/commit/84a401f0fa3095e0a19661670d1570d0c3b9d3c9))


### Reverts

* revert 16.0.0 CHANGELOG entry ([920320a](https://www.github.com/yargs/yargs-parser/commit/920320ad9861bbfd58eda39221ae211540fc1daf))
