# 这里记录日常积累的知识点

## Cakephp 

### save&update
使用save和updateAll 方法时，有时会遇到带引号的字符串，直接保存会报错，可以使用下面的方法：

````
$db = $this->model->getDataSource();
$db->value($value,'string');
````    

### Cakephp 文件目录权限修正

````
HTTPDUSER=`ps aux | grep -E 'nobody|[n]ginx' | grep -v root | head -1 | cut -d\  -f1`
setfacl -R -m u:${HTTPDUSER}:rwx app/tmp
setfacl -R -d -m u:${HTTPDUSER}:rwx app/tmp
````

## Laravel 目录权限设置

````
HTTPDUSER=`ps aux | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root | head -1 | cut -d\  -f1`
setfacl -R -m u:${HTTPDUSER}:rwx storage/
setfacl -R -m u:${HTTPDUSER}:rwx bootstrap/cache/
````