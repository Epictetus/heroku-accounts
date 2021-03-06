# Heroku Accounts

Helps use multiple accounts on Heroku.

## Installation

    $ heroku plugins:install git://github.com/ddollar/heroku-accounts.git

## Usage

To add accounts:

    $ heroku accounts:add personal
    Enter your Heroku credentials.
    Email: david@heroku.com
    Password: ******

    Add the following to your ~/.ssh/config

    Host heroku.personal
      HostName heroku.com
      IdentityFile /PATH/TO/PRIVATE/KEY
      IdentitiesOnly yes

Or you can choose a fully-automated approach:

    $ heroku accounts:add work --auto
    Enter your Heroku credentials.
    Email: work@example.org
    Password: ******
    Generating new SSH key
    Generating public/private rsa key pair.
    Your identification has been saved in ~/.ssh/identity.heroku.work.
    Your public key has been saved in ~/.ssh/identity.heroku.work.pub.
    Adding entry to ~/.ssh/config
    Adding public key to Heroku account: work@example.org

To switch an app to a different account:

    # in project root
    heroku accounts:set personal

To list accounts:

    $ heroku accounts
    personal
    work

To remove an account:

    $ heroku accounts:remove personal
    Account removed: personal

Set a machine-wide default account:

    $ heroku accounts:default personal
