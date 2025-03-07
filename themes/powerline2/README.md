# Powerline2 Theme

A colorful theme, where shows a lot information about your shell session.

**IMPORTANT:** This theme requires that [a font with the Powerline symbols](https://github.com/powerline/fonts) needs to be used in your terminal emulator, otherwise the prompt won't be displayed correctly, i.e. some of the additional icons and characters will be missing. Please follow your operating system's instructions to install one of the fonts from the above link and select it in your terminal emulator.

**NOTICE:** The default behavior of this theme assumes that you have sudo privileges on your workstation. If that is not the case (e.g. if you are running on a corporate network where `sudo` usage is tracked), you can set the flag 'export THEME_CHECK_SUDO=false' in your `~/.bashrc` or `~/.bash_profile` to disable the Powerline theme's `sudo` check. This will apply to all `powerline*` themes.

## Provided Information

* Current path
* Current username and hostname
* Current time
* An indicator when connected by SSH
* An indicator when `sudo` has the credentials cached (see the `sudo` manpage for more info about this)
* An indicator when the current shell is inside the Vim editor
* Battery charging status (depends on the [../../plugins/battery/battery.plugin.sh](battery plugin))
* SCM Repository status (e.g. Git, SVN)
* The current Python environment (Virtualenv, venv, and Conda are supported) in use
* The current Ruby environment (rvm and rbenv are supported) in use
* Last command exit code (only shown when the exit code is greater than 0)

## Configuration

This theme is pretty configurable, all the configuration is done by setting environment variables.

### User Information

By default, the username and hostname are shown, but you can change this behavior by setting the value of the following variable:

    POWERLINE_PROMPT_USER_INFO_MODE="sudo"

For now, the only supported value is `sudo`, which hides the username and hostname, and shows an indicator when `sudo` has the credentials cached. Other values have no effect at this time.

### Clock Format

You can change the format using the following variable:

    THEME_CLOCK_FORMAT="%H:%M:%S"

The time/date is printed by the `date` command, so refer to its man page to change the format.

### Segment Order

The contents of the prompt can be "reordered", all the "segments" (every piece of information) can take any place. The currently available segments are:

* battery
* clock
* cwd
* in_vim
* python_venv
* ruby
* scm
* user_info

A variables can be defined to set the order of the prompt segments:

    POWERLINE_PROMPT="user_info scm python_venv ruby cwd"

The example values above are the current default values, but if you want to remove anything from the prompt, simply remove the "string" that represents the segment from the variable.


![powerline2 example](https://github.com/Matiusco/oh-my-bash/blob/master/themes/powerline2/powerline2-dark.png)
