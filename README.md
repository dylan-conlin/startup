**Installation**

install the [heroku toolbelt](https://toolbelt.heroku.com/) to get foreman

    git clone https://github.com/fellytone84/startup.git ~/.config
    gem install consular 
    gem install consular-osx    # if using Terminal
    gem install consular-iterm  # if using iTerm
    consular init               # this will create your .consularc

add one of the following lines to your `.consularc`:

    require "consular-osx"      # if using Terminal    
    require "consular-iterm"    # if using iTerm    

configure the following variables in your `.bash_profile` or `.zprofile`:

    # configure the paths below to match the location of each app. Make
    # set each path starting from your ~/ directory

    export SHORTSTACK_PATH="~/sites/shortstack"
    export MESSAGING_PATH="~/sites/shortstack-messaging"
    export TABSERVER_PATH="~/sites/shortstack-server"
    export ADMIN_PATH="~/sites/shortstack-admin"
    export DESIGNER_PATH="~/sites/shortstack-designer"

(after saving your bash profile, don't forget to restart your Terminal--I always forget about this)

Finally, to avoid any port conflicts, I setup the default configuration to look for a `Procfile.dev` in each app's root directory. If you don't want to create a development procfile and would like to use the production `Procfile` instead, configure each consular script as follows:


in each script inside `~/.config/`, replace
    
    run "foreman start -f Procfile.dev"

with

    run "foreman start"

**Example Command Line Usage**

    consular list # lists all available consular scripts
    consular start shortstack                                  # starts shortstack via foreman
    consular start all                                         # starts all apps
    consular start shortstack; consular start designer         # starts shortstack and designer

and don't forget about typing `control-r consular` from the command line to get at your previous commands!