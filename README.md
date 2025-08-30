# Swift For Arduino Organisation

This is a place for the community to gather and share projects. Most people will be interested in the community repository, which is where we share programs actually written with the S4A IDE itself. Libraries that help people use peripherals for example.

If you really want to contribute to the S4A project, either documenting your projects, with youtube and social media and/or contributing code here are the best way to make this grow.

We can get contributions for the internal platform libraries or even compiler patches from advanced users, but these are typically less useful to be honest. Sample code and documentation of projects (hardware AND code) are the most useful thing for getting buzz and helping new people join the community.

Team notes
***

For core team members and other close collaborators, you will have access to some of the private (non open source) code repositories here, such as the IDE source code and the AVR library source code.

S4A, uSwift-ARM, uSwift-AVR, sec, gpl-tools-avr, ide-support-avr : these are the S4A IDE internal source code repositories.

AVR2, uSwiftShims : these are the AVR library and the microswift standard library (we intend to split these and fully open source the microswift standard library soon)

swift : this is a temporary compiler fork, it remains functionally identical to the public/open source fork github.com/carlos4242/swift. The only difference is it has our CI actions (github actions), and our self hosted runners can build with it. And it typically has one commit ahead of open source containing some sensitive notes and paths that are implementation details of our CI builds.

For security reasons we don't allow our self hosted runners to build from the open source repositories. (This is a standard security precaution.)

Adding a new runner (core team only)
***

To add a new github actions self hosted runner, go into Settings, Actions, Runners and select the New Runner button, then follow the steps. Only Apple Silicon Macs are suitable for our builds, and you won't be able to build pretty much anything unless you have Xcode 16.2. In terms of labels, allow the default labels (self-hosted, macOS, ARM64), and also add these labels to indicate what features you have on your mac for the CI to use:
xcode-16.2 [you have Xcode 16.2 installed in /Applications/Xcode-16.2.app] ... this is needed for most build jobs, including the IDE build
cmake [you have CMake 3.4 or later installed in /Applications/CMake.app] ... this is only needed if you want your runner to be able to build our open source swift compiler
avrgcc [you have avr-gcc installed via Homebrew] ... this is only needed if you want your runner to be able to compile the standard library and/or the AVR library
