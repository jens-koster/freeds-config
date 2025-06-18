# freeds-config
I've separated the config files to this repo to allow forking and maintaining personal config versions without having to fork the entire thing.


## "configs" folder
These are the config files for the default plugins and freeds itself. As more plugins are added this folder will grow and as long as you stick to default configs you just update it.

Some config files contain secrets. Since nothing in the free data stack is exposed outside the host they're not VERY secret, but yet, we don't put stuff named "secret_key" on github.
A template is proved for these files. You're expected to make a local copy of this folder named "secrets" and that's the one that will be used.
So, any new plugin secrets will have to be manually copied from here to the secrets folder (and edited).

## "locals" folder
The "locals" folder is created during setup and stays on your local storage, it should never be committed to git.
locals is for configs that are expected to be changed for each installation, like those containing secrets and one or two local directory locations.
If the same file is found in configs and locals, the locals one takes precedence. i.e. you wanna change a config, first copy it to locals. Then you can keep pulling this repo into configs and keep your local changes. Locals override file by file, changes in the config files will have to be merged manually.

Files with secrets and the freeds local config file will be copied to locals on setup. Some will be filled in by the setup process but manually editing is perfectly fine and probabaly necessary for the s3 config.

The currently known files to copy are:
* airflow.yaml (contains password)
* freeds.yaml (contains the location where the other freeds repos are cloned)
* minio.yaml (contains the admin user and password for minio S3 admin console)
* S3.yaml (contains the access keys for S3)
