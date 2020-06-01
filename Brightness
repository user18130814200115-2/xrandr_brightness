#!/bin/sh
displays=(HDMI-1 DP-0)

for i in "${displays[@]}"; do
	new=$(echo "$(xrandr --verbose --current | grep ^$i -A5 | tail -n1 | cut -f 2 -d ':')+$1" | bc)

	[ $(echo $new "< 1.1" | bc -l) = $(echo $new "> -0.1" | bc -l) ] && xrandr --output "$i" --brightness "$new"

done
