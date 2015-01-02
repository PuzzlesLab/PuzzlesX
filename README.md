PuzzlesX
========

PuzzlesX is the repository and documentations for Puzzles EDX platform used.

Configure Site Name
----------------------------

If want to change the site name for port 80, can go to `edx/app/edxapp`, edit both `lms.env.json` & `cmd.env.json` to update the platform name.

If want to change the studio, can go to `edx/app/edxapp/edx-platform/lms/envs/common.py`, inside there is a host name that you can configure. That will affect whole studio site name. (All the desired change variable should be in here, if not can be found on `edx/app/edxapp/edx-platform/cms/envs/common.py`)

**-> After update the platform name, please run the command for restarting LMS/CMS = `sudo /edx/bin/supervisorctl -c /edx/etc/supervisord.conf restart edxapp:` and workers = `sudo /edx/bin/supervisorctl -c /edx/etc/supervisord.conf restart edxapp_worker:`. After that you may notice the changes**

Custom Theme
--------------------

If you wish to change the current theme that used in EDX, please go to the following path:

`/edx/app/edx_ansible/`

There is a file call `server-vars.yml`. You may choose which custom theme that you would like to change. 

 <blockquote>
	<p>edxapp_use_custom_theme: true</p>
	<p>edxapp_theme_name: 'puzzlesxTheme'</p>
	<p>edxapp_theme_source_repo: 'https://github.com/rayson1223/puzzlesxTheme.git'</p>
	<p>edxapp_theme_version: 'HEAD'</p>
</blockquote>

If you wish to disable the usage of custom theme in EDX, just set `edxapp_use_custom_theme:` to `false`. 

After you had done the configurations, please type the command below to run the updates on EDX site.

`sudo /edx/bin/update edx-platform master`

--> This theme will only affect the theme for CMS of EDX. LMS currently are not available for theme editing. 

**If you lines are unstable, and keep broken pipe in the process of update, please use `tmux` that available in the console. For more information please checkout [here](https://gist.github.com/MohamedAlaa/2961058).**
