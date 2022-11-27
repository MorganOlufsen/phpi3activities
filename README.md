# phpi3activities

## What?

A dead-simple PHP script to group i3workspaces into activities, similar to KDE activites but
just for workpsaces.

looks like this:

![Sample image i3activities](https://raw.githubusercontent.com/MorganOlufsen/phpi3activities/main/image.png?token=GHSAT0AAAAAAB3RO4ZMJYWFNJTFO22FFVWGY4DYQRQ)

## Use case

- Work Project 1 (Activity)
	- workspace 1 (for example an ide with your project 1)
	- workspace 2 (terminals related to project 1)

- Project 2 (Activity)
    - workspace 1 (for example an ide with your project 2)
	- workspace 2 (terminals related to project 2)

- Personal (Activity)
	- workspace 1 (watever)
	- workspace 2 (watever)

- All Activities workspaces
	- workspace 7 (mail)
	- workspace 8 (docs)

## Usage

[mod]+[n] : Swith to workspace [n] in current selected activity
[mod]+[shift]+[n] : Send current window to workspace [n] in current selected activity
[mod]+[ctrl]+[n] : select current activity, set it to [n]


## Requirements

PHP, i3

## installation

Install php-cli
Download i3control
chmod u+x i3control

Move that file into your $PATH, or just use a full file route on "Configuration i3"

## Configuration, i3

Comment or remove workspace switching shortcuts in your i3 config file, add this lines to call i3control
instead:


```

# workspace focus

bindsym $mod+1 exec --no-startup-id "i3control focus 1"
bindsym $mod+2 exec --no-startup-id "i3control focus 2"
bindsym $mod+3 exec --no-startup-id "i3control focus 3"
bindsym $mod+4 exec --no-startup-id "i3control focus 4"
bindsym $mod+5 exec --no-startup-id "i3control focus 5"
bindsym $mod+6 exec --no-startup-id "i3control focus 6"
bindsym $mod+7 exec --no-startup-id "i3control focus 7"
bindsym $mod+8 exec --no-startup-id "i3control focus 8"
bindsym $mod+9 exec --no-startup-id "i3control focus 9"
bindsym $mod+0 exec --no-startup-id "i3control focus 10"


# Move to another workspace

bindsym $mod+Shift+1 exec --no-startup-id "i3control move_to 1"
bindsym $mod+Shift+2 exec --no-startup-id "i3control move_to 2"
bindsym $mod+Shift+3 exec --no-startup-id "i3control move_to 3"
bindsym $mod+Shift+4 exec --no-startup-id "i3control move_to 4"
bindsym $mod+Shift+5 exec --no-startup-id "i3control move_to 5"
bindsym $mod+Shift+6 exec --no-startup-id "i3control move_to 6"
bindsym $mod+Shift+7 exec --no-startup-id "i3control move_to 7"
bindsym $mod+Shift+8 exec --no-startup-id "i3control move_to 8"
bindsym $mod+Shift+9 exec --no-startup-id "i3control move_to 9"
bindsym $mod+Shift+0 exec --no-startup-id "i3control move_to 10"

# Configure 3 activities

bindsym $mod+Control+1 exec --no-startup-id "i3control set_project 1"
bindsym $mod+Control+2 exec --no-startup-id "i3control set_project 2"
bindsym $mod+Control+3 exec --no-startup-id "i3control set_project 3"

# Use activity 1 by default

exec --no-startup-id "i3control set_project 1"
exec --no-startup-id "i3control focus 1"
````

## Configuration, excluded workspaces

Edit i3control, and check for the "excludes" array at the begining,
those workspaces will be shared among all activities.

For example: [mod]+7 always go to workspace 'mail'.

````
$excludes = array(
	'5' => 'gimp',
	'6' => 'www',
	'7' => 'mail',
	'8' => 'docs',
	'9' => 'media',
	'10' => 'game',
);
````





