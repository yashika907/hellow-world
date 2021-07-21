
# hello-world

#script to download & activate & run wp-sweep plugin on wordpress
#!/bin/bash

WP="/usr/local/bin/wp --allow-root --skip-themes --skip-plugins"

read -p "Activate wp-sweep? (y/n) " REP
if [ "$REP" = "y" ]; then
 echo "INSTALLING WP-SWEEP"
${WP} plugin install wp-sweep 
 echo " "
 echo "ACTIVATING WP-SWEEP"
${WP} plugin activate wp-sweep
  echo " "
  echo "RUNNING sweep --all"
/usr/local/bin/wp --allow-root sweep --all
  echo " "  
echo "DEACTIVATING WP-SWEEP"
${WP} plugin deactivate wp-sweep
else
  echo "wp-sweep NoT Activated"
fi


#script ends here
