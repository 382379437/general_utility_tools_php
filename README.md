# php_date_deal_tool

#### 介绍
PHP日期处理工具
1. 日期加上N年、月、日、时、分、秒，得到计算后的时间
2. 两个日期相减得到天、时、分、秒（没有两个日期相加一说）
3. 更多更完善功能敬请期待......

#### 软件架构
软件架构说明


#### 安装教程

    composer require wanghua/php-date-deal-tool dev-master

#### 使用说明

##### 初始化
    $date = (new Date());
    $date->date_format = 'Y-m-d H:i:s';//设置格式，默认Y-m-d H:i:s
    
### 日期类型参数(第2个参数)可选项：
    //分、时、天、周、月、年
    protected $data_type = [
        'm'         =>'minute',//分钟
        'minute'    =>'minute',//分钟
        'h'         =>'hour',//小时
        'hour'      =>'hour',//小时
        'd'         =>'day',//天
        'day'       =>'day',//天
        'w'         =>'week',//周
        'week'      =>'week',//周
        'M'         =>'month',//月
        'month'     =>'month',//月
        'y'         =>'year',//年
        'year'      =>'year',//年
    ];
    
    
##### 在当前时间基础上加3天（第三个参数不传默认使用当前时间）
    $res = $date->addTime(3, 'd');//支持单词和字母，例如：d表示天，day也表示天
    dump($res);

##### 在当前时间基础上加1小时（第三个参数不传默认使用当前时间）
    $res = $date->addTime(1, 'h');//支持单词和字母，例如：h表示小时，hour也表示小时
    dump($res);

##### 在指定时间基础上加1小时
    $res = $date->addTime(1, 'h', strtotime('2010-10-01 12:00:10'));
    dump($res);
    
##### 在指定时间基础上减1个月 （注意：月是大写M字母，分钟是小写m字母）
    $res = $date->reduceTime(1, 'M', strtotime('2010-10-01 12:00:10'));
    dump($res);
    
##### 在指定时间基础上减20分钟 （注意：分钟是小写m字母）
    $res = $date->reduceTime(20, 'm', strtotime('2010-10-01 12:00:10'));
    dump($res);
    
##### 在指定时间基础上减1年 
    $res = $date->reduceTime(1, 'y', strtotime('2010-10-01 12:00:10'));
    dump($res);

### 日期时间相减

    //时间相减返回的时间类型 秒、分、时、天 默认返回秒
    protected $time_type = [
        's'         =>1,//秒
        'second'    =>1,//秒
        'm'         =>60,//分钟
        'minute'    =>60,//分钟
        'h'         =>3600,//小时
        'hour'      =>3600,//小时
        'd'         =>86400,//天
        'day'       =>86400,//天
    ];

    $start_time = '2010-05-01 12:30:00';
    $end_time = '2010-10-28 12:30:00';
    
    //结束时间减去开始时间得到秒数 (返回类型参考上方配置)
    $res = $date->timeReduceTime($end_time, $start_time);
    dump($res);
    
    //结束时间减去开始时间得到天数 (返回类型参考上方配置)
    $res = $date->timeReduceTime($end_time, $start_time, 'day');
    dump($res);

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
