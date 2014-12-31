PuzzlesX
========

PuzzlesX is the repository and documentations for Puzzles EDX platform used.



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
