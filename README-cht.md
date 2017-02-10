# ubus-scriptd

ubus-scriptd主要自動帶起ubus service 
因此只要停止ubus-scriptd，將會停止自動被帶起的ubus service

ubus-scriptd有下例程序:
* app_load_services
 * 由/usr/lib/ubus-services目錄加入ubus service 
 * 目前只提供使用lua寫的程式

* app_load_scripts
 * 由/usr/lib/ubus目錄加入ubus service 
 * 目前可以存放binary及script，需要依據使用方式

* app_load_script程序
 * 讀取/usr/lib/ubus檔案，並且執行檔案帶參數(.methods) 
 * 此時程式需要回應ubus mehtod的json檔案，並將此method加入obj 
 * 檔有人通過ubus call會將參數帶入執行檔 
 * ex. /usr/lib/ubus cmd-json
   
* 其它參考說明 
   [Writing a ubus script][1]
   
[1]:http://mkschreder.github.io/juci/manual/creating-pages.html
