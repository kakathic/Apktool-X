#### Apktool X Update

##### Version=1

su -c echo 'locale=$(getprop persist.sys.locale|awk -F "-" '{print $1"_"$NF}')
  [[ ${locale} == "" ]] && locale=$(settings get system system_locales|awk -F "," '{print $1}'|awk -F "-" '{print $1"_"$NF}')
if [ "$locale" == "vi_VN" ];then
caiapk="- File Apk ở đường dẫn /sdcard/Apktool-X.apk"
else
caiapk="- Apk file in the path /sdcard/Apktool-X.apk"
fi

cp -rf /data/local/Tool-Apk/apktool/openjdk/lib/jli/Apktool-X.apk /sdcard
echo
echo -n "$caiapk"
kk() {
if [ -e /data/data/per.pqy.apktool ];then
ln -s /data/local/Tool-Apk/apktool /data/data/per.pqy.apktool/apktool
else
echo -n "."
sleep 2
kk
fi
}
kk' > /data/local/Tool-Apk/apktool_x
