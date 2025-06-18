# freeds-config
Config files and templates for the config files containing secrets.
I've separated the config files to this repo to allow forking and maintaining personal config versions without having to fork the entire thing.

## Config folder
These are the config files for the default plugins and freeds itself. As more plugins are added this folder will grow and as long as you stick to default configs you just update it

## Secrets_template folder
Some config files contain secrets. Since nothing in the free data stack is exposed outside the host they're not VERY secret, but yet, we don't put stuff named "secret_key" on github. 
These are template files. You're expected to make a local copy of this folder named "secrets" and that's the one that will be used.
So, any new plugin secrets will have to be manually copied from here to the secrets folder (and edited).






