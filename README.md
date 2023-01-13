font pango:Open Sans 1
set $mod Mod1
set $out_pri output eDP-1
set $out_sec output HDMI-1
bindsym $mod+w exec --no-startup-id firefox
bindsym $mod+a exec --no-startup-id nautilus
bindsym $mod+e exec --no-startup-id kate
bindsym $mod+q exec --no-startup-id lowriter
bindsym $mod+g exec --no-startup-id google-chrome-stable
bindsym $mod+s exec --no-startup-id alacritty
bindsym $mod+z kill
bindsym $mod+x restart
bindsym $mod+d exec --no-startup-id dmenu_run
bindsym $mod+Shift+a exec --no-startup-id dolphin
bindsym $mod+r exec alacritty -e vim .config/i3/config
bindsym $mod+k exec alacritty -e sudo pacman -Syyuu
bindsym $mod+l exec alacritty -e sudo pacman -Scc
bindsym $mod+control+Shift+z exec alacritty -e shutdown -h now
bindsym $mod+control+Shift+a exec alacritty -e reboot
bindsym $mod+F4 exec 'Yes, exit i3'
exec --no-startup-id dex --autostart --environment i3
exec --no-startup-id xrandr --output eDP-1 --brightness 0.4 &
exec --no-startup-id redshift -P -O 3800k &

# > ABRIR JANELAS PADRÃO EM MODO ABAS ##########
workspace_layout tabbed
# > CHANGE CONTAINER LAYOUT (stacked, tabbed, toggle split) - question = (?) ##########
bindsym $mod+control+Up layout toggle all
# > FULLSCREEN/no fullscreen apps - toggle = (auto-reverse) ##########
bindsym $mod+F11 fullscreen toggle

# > AJUSTE VOLUME AUDIO ##########
set $refresh_i3status killall -SIGUSR1 i3status
bindsym XF86AudioRaiseVolume exec --no-startup-id pactl set-sink-volume @DEFAULT_SINK@ +10% && $refresh_i3status
bindsym XF86AudioLowerVolume exec --no-startup-id pactl set-sink-volume @DEFAULT_SINK@ -10% && $refresh_i3status
bindsym XF86AudioMute exec --no-startup-id pactl set-sink-mute @DEFAULT_SINK@ toggle && $refresh_i3status
bindsym XF86AudioMicMute exec --no-startup-id pactl set-source-mute @DEFAULT_SOURCE@ toggle && $refresh_i3status

# > MUDAR FOCO ##########
bindsym $mod+Tab focus left
bindsym $mod+Down focus down
bindsym $mod+Up focus up
bindsym $mod+Right focus right
# > MOVER FOCO JANELA ##########
bindsym $mod+Shift+Left move left
bindsym $mod+Shift+Down move down
bindsym $mod+Shift+Up move up
bindsym $mod+Shift+Right move right

# > DEFINE NAMES for default workspaces ##########
set $ws1 "1"
set $ws2 "2"
set $ws3 "3"
set $ws4 "4"
set $ws5 "5"
# > SWITCH to workspace ##########
bindsym $mod+1 workspace number $ws1
bindsym $mod+2 workspace number $ws2
bindsym $mod+3 workspace number $ws3
bindsym $mod+4 workspace number $ws4
bindsym $mod+5 workspace number $ws5
# > MOVE FOCUSED container to workspace ##########
bindsym $mod+Shift+1 move container to workspace number $ws1
bindsym $mod+Shift+2 move container to workspace number $ws2
bindsym $mod+Shift+3 move container to workspace number $ws3
bindsym $mod+Shift+4 move container to workspace number $ws4
bindsym $mod+Shift+5 move container to workspace number $ws5

# > BARRA DE TAREFA ##########
# bar {
#        status_command i3status
# }

# > WIRELESS - NetworkManager is the most popular way to manage wireless networks on Linux ##########
# exec --no-startup-id nm-applet
# > MUDAR POSIÇÃO JANELA Mouse+$mod ##########
# floating_modifier $mod
# > SPLIT HORIZONTAL/VERTICAL - semicolon = (;) ##########
# bindsym $mod+semicolon split toggle
# > TOGGLE TILING/floating ##########
# bindsym $mod+Shift+space floating toggle
# > CHANGE FOCUS between tiling/floating windows ##########
# bindsym $mod+space focus mode_toggle
# > FOCUS THE PARENT container ##########
# bindsym $mod+J focus parent
# > FOCUS THE CHILD container ##########
# bindsym $mod+ focus child
# > MOVER JANELAS tiling drag & drop ##########
# tiling_drag modifier titlebar
# > RELOAD configuration file ##########
# bindsym $mod+Shift+c reload
# > BLOQUEIO DE TELA ##########
# exec --no-startup-id xss-lock --transfer-sleep-lock -- i3lock --nofork

