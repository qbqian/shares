#这里记录日常积累的知识点

##Cakephp 

### save&update
使用save和updateAll 方法时，有时会遇到带引号的字符串，直接保存会报错，可以使用下面的方法：

````
$db = $this->model->getDataSource();
$db->value($value,’string’);
````    