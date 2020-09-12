# tesla-remote (CLI)

Remote control your Tesla from the command-line. Written in CaffeineScript on NodeJS.

- Based on this NPM package: https://www.npmjs.com/package/teslajs
- Based on the unofficial Tesla API documention: https://tesla-api.timdorr.com

# Install

```
git clone git@github.com:shanebdavis/tesla-remote.git
cd tesla-remote
npm install
```

# Run

```
./tesla-remote
```

# Your Tesla Credentials

Your username and password are not stored. They can be passed on the command-line for each command, or they can be set in environment variables. The latter is the most secure since they will "go away" when you close your terminal.

How use with environment vars:

```bash
export tesla_username=foo@bar.com
export tesla_password=abc123
./tesla-remote vehicles
```

How use with commandline args:

```bash
./tesla-remote vehicles --username foo@bar.com --password abc123
```
