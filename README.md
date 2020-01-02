# displayplacer wrapper

Have you ever plugged your Macbook Pro into your usb-c dock only to realize that your screens have been swapped?  It is time consuming to reset the display arrangement when you have multiple external monitors which are set in different orientations.

This repository contains a wrapper script and two `Quick Actions` which interact with [displayplacer](https://github.com/jakehilborn/displayplacer) to reset your display arrangement to a desired configuration.

The quick actions can be added to a Macbook Pro's Touch Bar control strip which allows you to reset your display arrangement with only a few taps on the Touch Bar.

## Setup

## Prerequisites 

[Homebrew](https://docs.brew.sh/Installation) must be installed on your machine prior to using this wrapper script.

### Installation

Run the following commands below, replacing `<user>` with a real user name.

```sh
cd ~
git clone git@github.com:njtman/displayplacer_wrapper.git
ln -s /Users/<user>/displayplacer_wrapper/displayplacer_wrapper /usr/local/bin/displayplacer_wrapper
```

Note - Ensure that `/usr/local/bin/` is added to your `PATH` variable so invocations to `displayplacer_wrapper` can successfully execute.

## How to use

### Quick actions

This repository contains two `Quick Actions` to make interactions with the wrapper script more convenient.

Double click on `fix_displays.workflow` and `save_display_arrangement.workflow` to install the two Quick Actions.

Perform the following steps to make the newly installed Quick Actions available on the Touch Bar:

0. Open the macOS `Settings` app
0. Click `Keyboard`
0. Click `Customize Control Strip...`
0. Drag the `Quick Actions` icon down to the Touch Bar.

`Save display arragement` and `Fix displays` will now be visible on the Touch Bar after tapping the `Quick Actions` icon.

#### Save display arrangement

This Quick Action will persist the current display arrangement to a configuration file located in `$HOME/.displayplacer.cfg`.

This Quick Action must be run at least once before running `Fix displays`.

#### Fix displays

This Quick Action will set the display arrangement using the previously persisted values from running the `Save display arragement`.

It is normal for the display to go blank for a couple of seconds while setting the display arrangement.

### CLI

If you prefer interacting with the wrapper script using the CLI, continue reading below.

#### Saving the current display arrangement

0. Navigate to the `Settings`app in macOS, then click `Displays`, and go to the `Arrangement` tab.  Configure the displays to a desired configuration.
0. Open the `Terminal` app and type in `displayplacer_wrapper save`.  This will persist the current display arrangement to a configuration file located in `$HOME/.displayplacer.cfg`.

#### Applying the previously saved display arragement

0. Open the `Terminal` app and type in `displayplacer_wrapper apply`.
