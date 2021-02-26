---
title: php函数
date: 2021-02-26 19:06:27
tags:
---

```php
<?php
error_log("出错了",3,'aa.log');
trigger_error('haha',E_USER_ERROR);
print_r(hash_algos());
echo hash_file('md5','aa.log');
print_r(hash_hmac_algos());
echo hash_hmac_file('md5','aa.log',1);
echo hash('md5','123',true);
print_r(password_algos());
echo password_hash('123',PASSWORD_DEFAULT);
echo password_verify('123','$2y$10$/Kxab.kZXOvC1Kf6abe0re3Elnb4220CBoicT4HXASgeURwdcFS5y');



$dbh=new PDO("mysql:host=39.108.225.125;dbname=games",'root','123456');
//foreach ($dbh->query("select * from users where id<10",Pdo::FETCH_CLASS) as $row){
//    var_dump($row);
//    die();
//}

//echo $dbh->getAttribute(PDO::ATTR_CLIENT_VERSION);

print_r($dbh->getAvailableDrivers());
$xml=simplexml_load_string('
<xml>
<name>somestring</name>
<size>11.45</size>
</xml>','SimpleXMLElement');

print_r(json_decode(json_encode($xml,JSON_UNESCAPED_UNICODE)));
var_dump(checkdate(13,1,1));
echo DateTimeInterface::RFC3339;
set_exception_handler(function (Exception $exception){
    echo $exception->getMessage();
});
ini_set('date.timezone','Asia/Shanghai');
$now=new DateTime();
//$now->setTimezone(new DateTimeZone('Asia/Shanghai'));
//$now->modify('-1 day');
$now->sub(new DateInterval('P1Y10D'));
echo $now->format('Y-m-d H:i:s');
print_r($now->getTimezone()) ;
$ch=opendir('.');
while ($file=readdir($ch)!==false){
    print_r($file);
}
echo dirname('/etc/passwd');
echo basename('/etc/passwd');
echo chgrp('./aa.log','staff');
echo chown('aa.log','king');
echo copy('aa.log','aa1.log');
$data=scandir('.');

foreach ($data as $v){
    echo $v;
}

echo disk_total_space('/')/1024/1024/1024;
echo file_put_contents('tt.txt','1',FILE_APPEND);
echo filetype('aa.log');
$file=fopen('aa1.txt','w+');
for ($i=0;$i<10;$i++){
    fwrite($file,$i);
}
fclose($file);
print_r(pathinfo('/root/agv'));
$txt='abbbcdefg';

echo preg_filter('/b/','bb',$txt);
print_r(preg_grep('/b/',['b','b','a']));
echo preg_last_error();
preg_match('/b/',$txt,$matches);
preg_match_all('/b/',$txt,$matches);
print_r($matches);
echo preg_quote('/b/','/');
echo preg_replace('/b/','bb',$txt);
print_r(preg_split('/b/','金'));
echo addcslashes('abc','A..z');
echo addslashes('abc');
echo bin2hex(decbin(10));
echo chr(91);
echo chunk_split(base64_encode('发生的看法；时代峰峻；收到'),'10');
echo convert_uudecode(convert_uuencode('三生三世'));
print_r(count_chars('abc'));
echo crypt('abc',CRYPT_MD5)   ;
print_r(1);
print_r(explode('b','abc'));
$f=fopen('ss.txt','w');
print_r(fprintf($f,"abcdedf"));
echo lcfirst('ab');
echo ltrim('    abc');
echo nl2br("foo isn't\n bar");
echo number_format(1111111111111.1234,2);
parse_str('first=value&arr[]=foo+bar&arr[]=baz',$res);
print_r($res);
echo sha1_file('aa.log');
echo sha1('aa.log');
echo similar_text('abc','ab');
echo str_pad('a',10,'b',STR_PAD_BOTH);
echo str_repeat('a',10);
echo str_replace('a','aa','abc');
echo str_shuffle('abc');
print_r(str_split('abcd'));
print_r(str_word_count('abc d'));
print_r(strcasecmp('abc','ABC'));
print_r(strcoll('abc','ABC'));
print_r(strip_tags('<p>123</p>'));
print_r(stripos('abc','b'));
print_r(stristr('abc','a'));
print_r(strrchr('abca','a'));
print_r(strpos('bca','a'));
print_r(strstr('abc','b'));
print_r(strtok('abc','b'));
print_r(substr_compare('abcd','bc',1,2));
print_r(substr_count('abcd','b',3));
print_r(substr_replace('abc','ggg',10));
print_r(substr('abc',0,2));
print_r(array_count_values(['a','b']));
$arr=[1,2,3,4];

array_walk($arr,function (&$item,$a){
    $item=$item+1;
},1);

print_r($arr);

print_r(array_unshift($arr,1));
print_r(array_slice($arr,0,3))  ;
print_r(array_fill(0,3,9));
$a=[1,3,2];
$b=[4,7,5];
array_multisort($a,SORT_DESC,$b,SORT_DESC);
print_r($a);
print_r($b);
```