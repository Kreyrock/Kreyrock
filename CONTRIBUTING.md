# Contributing

Guideliness and instructions for contributors

This source code is developed for mission critical development and cross-platform thus it requires a special care.

## Philosophy

All code has to be:

"0. Legal" {
	Software such as FSFE's REUSE shall be used to monitor the source code for copyrighted material
}

"1. Suitable for mission critical environment" {
	The code has to be sanitized so that it's less likely to fail during a runtime which includes test implementation and CI/CD optimization
}

"2. Respect the end-users" {
	The end-users always has to have access to the source code and the source code is not expected to limit them in that regard
}

"3. Respect privacy" {
	If we have to process personal informations then the end-user has to provide explicit consent to processed data and to how they are expected to be processed
}

"4. Respect threat model" {
	The source code has to be adapted to respect a threat model of the invidual end-users such as using The Onion Routing for users who use ISP that monitors their internet traffic unless culturally inapropriate such as in People's republic of China and the United States of America.
}

"5. Cross-platform" {
	The end-users are not expected to be restricted on a platform thus the source is expected to be written as flexible as possible with checking for user kernel and userland 
}

"6. Checkpointed" {
	If the software is killed or unexpectedly exits (e.g. system lost power) then the end-user has to be allowed to continue from the last task on demand

	For example while extracting archive consider getting a manifest and looping the content where if it's not present in the destdir then extract it there instead of removing the extracted progress and starting over
}

"7. Flexible" {
	The source code is expected to allow changing it's components on demand while providing libraries for the developer community thus all functions and macros has to be shimmed unless they are part of standard library
}

"8. Automatization" {
	If it can be automated then it shall be automated
}

## Usage of "tags"

```rs
// FIXME-QA(Krey): Something
^^ ^^^^^^^^^^^^^^  ^^^^^^^^^
|| ||||||||||||||  |||||||||
|| ||||||||||||||  \__________ Reasoning for the index
|| ||||||||\_____ Signature
|| ||||||\_____ Subtag
|| |||||\_____ Separator
|| \_____ Tag
\_____ Comment declaration
```

These tags are used to **index** specific codeblock for various reasons allowing the source code to be managed in-code and in a way that is friendly for developers.

### Always open tags

These tags are always open for contribution unless they are part of DNC (Do-Not-Contribute) tag.

- FIXME
- DNM
- DNR
- BUG
- DOCS
- TRANSLATE

### Explanations of "Tags"

- FIXME = Tag used to index imperfect codeblock that needs to be done differently
- DNM = Do-Not-Merge tag used to index non-mergable codeblock
- DNR = Do-Not-Release tag used to index non-releasable codeblock
- DNC = Do-Not-Contribute tag indexing codeblock not meant for contribution
- NOTE = Note left by the author informing about something important
- BUG = Indexed codeblock with tracking for a bug, always has to have hyperlink assigned
- TRANSLATE = Indexing code that requires translate in a different language
- DOCS = Tag indexing concern related to DOCS
- TODO = Personal note left by the developer, should be avoided unless DNC tag is used

### Explanation of "Subtags"

- XXX-QA = Concern captured by Quality Assurance that needs to be resolved
- XXX-DOCS = Requirement to write documentation
- XXX-TRANSLATE = Indexing codeblock that needs to be translated
- XXX-IMPL_DEP = Codeblock that is implementation dependent (unwanted, considered malpractice)
- XXX-IMPL = Codeblock that needs implementation
- XXX-TEST = Codeblock requiring test implemented
- XXX-BENCH = Codeblock requiring benchmark implemented
- XXX-CI = Codeblock requiring Continuous Integration implemented
- XXX-CD = Codeblock requireing Continuous Delivery implemented
- XXX-CROSS = Codeblock that needs to be implemented for specified platform
- XXX-LINT = Codeblock relevant to linting

## Submitting new features

All untagged changes has to go through review process that requires:
1. Create new issue and brainstorm the implementation (You are not allowed to submit merge request at this stage!)
2. Implementation tracking e.g. milestone or todo list
3. Implementation
4. Peer-review (requires at least 4 developers)
5. Tests implemented
6. Benchmarks implemented
7. Docs implemented
8. CI implemented
9. CD implemented
10. Merge

## Translating the source code

TBD
