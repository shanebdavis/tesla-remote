# tesla-remote (CLI)

> WARNING: EXPERIMENTAL - This is all unofficial. Use at your own risk. Remember, you are remote controlling a large, expensive object. Remember there are objects nearby. Make sure you think carefully before taking any "write" actions.
<br><br>That said, currently there are no commands to *move* the car. The biggest risk is opening or closing the trunk when there is something to bump into, or... accidentally leaving your windows open or car unlocked.

**tesla-remote** is a remote control your Tesla. It is written in CaffeineScript (JavaScript in 1/3 the code) and runs on NodeJS.

- Based on this NPM package: https://www.npmjs.com/package/teslajs
- Based on the unofficial Tesla API documentation: https://tesla-api.timdorr.com

# Run

Be sure to install [NodeJS](https://nodejs.org/en/download/) if you haven't already, then run the following for the latest CLI help:

```bash
npx tesla-remote
```

# About Your Tesla Credentials

Your username and password are not stored. They can be passed on the command-line for each command, or they can be set in environment variables. The latter is the most secure since they will "go away" when you close your terminal.

How to use with environment vars:

```bash
# TIP: For the best security, put a space before the "export" commands.
# That way they won't be saved to your shell's command history.
 export tesla_username=foo@bar.com
 export tesla_password=abc123
npx tesla-remote vehicles
```

How to use with command-line arguments:

```bash
npx tesla-remote vehicles --username foo@bar.com --password abc123
```

# Clone and Play!

This tool is mostly a tech demo, and the most fun is opening up the code and customizing it:

```bash
git clone git@github.com:shanebdavis/tesla-remote.git
cd tesla-remote
npm install
```
