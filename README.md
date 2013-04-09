install the [heroku toolbelt](https://toolbelt.heroku.com/) to get foreman

    gem install consular
    gem install consular-osx    # if using Terminal
    gem install consular-iterm  # if using iTerm
    git clone https://github.com/fellytone84/startup.git ~/.config

configure the following variables in your `.bash_profile` or `.zprofile`:

    # configure the paths below to match the location of each app. Make
    # set each path starting from your ~/ directory

    export SHORTSTACK_PATH="~/sites/shortstack"
    export MESSAGING_PATH="~/sites/shortstack-messaging"
    export TABSERVER_PATH="~/sites/shortstack-server"
    export ADMIN_PATH="~/sites/shortstack-admin"
    export DESIGNER_PATH="~/sites/shortstack-designer"

Finally, to avoid any port conflicts, I setup the default configuration to look for a `Procfile.dev` in each app's root directory. If you don't want to create a development procfile and would like to use the production `Procfile` instead, configure each consular script as follows:



in each script inside `~/.config/`, replace
    
    run "foreman start -f Procfile.dev"

with

    run "foreman start"