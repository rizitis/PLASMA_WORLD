# ATHOS

These are requitments in order to use **AthOS**:


## slackdesc
When you ran `sudo bash setup.sh` slackdesc script will be symlinked in /usr/local/bin/slackdesc so you are fine. 
You may read [here](https://slack-desc.sourceforge.net) about it.<br>
If this tool is installed then no separate slack-desc files needed for your builds. Just add discription in pkg.ini and app slackdesc will create and install a valid slack-desc for the specific pkg we are building.<br>
You can always skip or rm  slackdesk script from your system and continue creatings slack-desk manually, athos will work with them.<br>


### doinst.sh

If your build need a usual doinst.sh then **you dont** have to create it, athos is prepare for that also. <br>
Only in very rare special cases that a specific doinst.sh must ran after installation then you can create one manually before build and athos will respect your choise. Or create one in slackbuild() function.<br>
```
mkdir -p "$PKG"/install
cat <<EOF > "$PKG"/install/doinst.sh
( add your commands )
( here line by line )
(leave an empty line at the end)
EOF
```

### dounist.sh
If you need a dounist.sh create one in $CWD/dounist.sh and athos know what to do...

### patches

If patches needed then you must create a folder named **patches** and put them in. athos will find them and apply to src.<br>
Just be sure that folder is named **patches** and not `patch` or `patche` also all diles **must** have the extension *.`patch`  etc...

