# tesla-remote (CLI)

> WARNING: EXPERIMENTAL - This is all unofficial. Use at your own risk. Remember, you are remote controlling a large, expensive object. Remember there are objects nearby. Make sure you think carefully before taking any "write" actions.
<br><br>That said, currently there are no commands to *move* the car. The biggest risk is opening or closing the trunk when there is something to bump into, or... accidentally leaving your windows open or car unlocked.

Use **tesla-remote** to get info and remote control your Tesla. It is written in CaffeineScript (JavaScript in 1/3 the code) and runs on NodeJS.

- Based on this NPM package: https://www.npmjs.com/package/teslajs
- Based on the unofficial Tesla API documentation: https://tesla-api.timdorr.com

# Quikc Start

Be sure to install [NodeJS](https://nodejs.org/en/download/) if you haven't already, then run the following for the latest CLI help:

```bash
# Get a list of your vehicles.
# NOTE: Your username and password are not stored anywhere.
# NOTE: The space before ' npx ...' ensures the command isn't stored
#       in your command-history.
 npx tesla-remote vehicles --username test@test.com --password abc123
```

# Run Multiple Commands

Above is the simplest way to run one command. Typically you'll want to run multiple commands, and you won't want to pass your username and password every time.
```bash
# Authenticate and store the auth-token in the shell's environment:
# NOTE: Your username and password are not stored.
# NOTE: An auth_token is stored in your shell's environment.
# NOTE: Your tesla_auth_token will be discard when you close your shell.
 export tesla_auth_token=`npx tesla-remote auth --username test@test.com --password abc123`

# Now run as many commands as you want.
# Bonus: It's safe to use your shell's command history.
npx tesla-remote vehicles
npx tesla-remote vehicle-data

# IMPORTANT: Don't forget to close your shell when you are done!
```



# Environment Variables

If you are issuing multiple commands, the best solution is to set your credentials and product-id as environment variables.

```bash
# NOTE:
#   Start any command that has your password or token with a "space" so
#   it doesn't get saved in your command history.

# the username/email you use to log in with
export tesla_username=test@test.com

# the password for your account
 export tesla_password=abc123

# alternatively, you can fetch the token once with the "auth" command:
# Get your authToken:
# >  tesla-remote auth --username test@test.com --password abc123
# qts-abc123abc123abc123abc123abc123abc123abc123abc123abc123abc123abc123
 export tesla_auth_token=qts-abc123abc123abc123abc123abc123abc123abc123abc123abc123abc123abc123

# select your vehicle
# Get your product id:
# >  tesla-remote vehicles
# []
#   id:           123456789012 <-- copy the 'id' field, not the 'vehicle_id' field
#   vehicle_id:   999999999999
export tesla_product_id=123456789012
```

# About Your Tesla Credentials

Your username and password are not stored. They can be passed on the command-line for each command, or they can be set in environment variables. The latter is the most secure since they will "go away" when you close your terminal.

How to use with environment vars:

```bash
# (add space before commands with sensitive information to signal
# to your shell not to save them to your command history)
export tesla_username=foo@bar.com
 export tesla_password=abc123
npx tesla-remote vehicles

# or
 export tesla_auth_token=qts-abc123abc123abc123abc123abc123abc123abc123abc123abc123abc123abc123
npx tesla-remote vehicles
```

How to use with command-line arguments:

```bash
# (add space before commands with sensitive information to signal
# to your shell not to save them to your command history)
 npx tesla-remote vehicles --username foo@bar.com --password abc123
```

# Clone and Play!

This tool is mostly a tech demo, and the most fun is opening up the code and customizing it:

```bash
git clone git@github.com:shanebdavis/tesla-remote.git
cd tesla-remote
npm install
```