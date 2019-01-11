# Platform.sh default demo

- Show the regions and options available (plan, storage)
- Create a project with the CLI and explains that it can be automated through the API when Gigster create their own project
- While the project is being created, show Accounts and how a user can get access to different projects
- Add the new p.sh remote to the example repo. Push to p.sh. If the push takes some time list the runtimes and services we support.

*For a short demo, do the above steps before the meeting.*

- Show the site. `platform ssh` to the environment and show the `php -v` version.
- `platform branch slider-<customer>`. Explain the “clone” process: we recreate new containers instances that are completely isolated (configuration and resources wise) and that we use Ceph to add a virtual layer on top of the FS so we can spawn those new envs in less than 2 minutes and get a “byte-to-byte” copy of the production environments: You are 100% sure to reproduce a bug or, the other way around, a feature working on a test env will be working on prod as well.
- Show the new environment in the console and http
- Open the example repo on the slider-<customer> branch and copy the html at the top of `demo.txt` to `index.php` line 237
- Open `platform.app.yaml` and update `php:7.0` to `php:7.2` and explain that as the configuration is tracked by git, we consider infrastructure changes as code and as a part of the project lifecycle. 
- `git commit -am “Add slider and update php version”. Do some joke about how it is hard right now to do those updates on traditional managed hosting systems and explain that you can also do that to add new services (elastic, etc.). 
- Show the site with the wonderful slider. 
- `platform ssh` to the environment and show the `php -v` version.
- Merge the environment through the interface and then show the slider in production.
- `platform ssh` to the `master` environment and show the `php -v` version.
- Finish by explaining the variables that are inherited and can be overridden and the permissions system to limit access to test environments for example for a 3rd party.
- If necessary, talk about the snapshot feature.