# 12306-PHP
12306火车票自动抢票PHP

每天忙着拍黄篇(PHP)，下班晚上凑合写了两天,配合charles，目前功能比较简单，代码也有些冗余囧……，但主功能基本具备，稍作修改可以引入框架使用。使用前先测测邮箱发送。

   - 环境
        - php>=5.6
        - Train.php 必须有写入权限，当前一些缓存型的文件都是自动生成（cookie、uamtk、newapptk、favorite_names）
        - curl、mail、额……总而言之TMD正常环境都没毛病，都是很常见的方法
   - 目录
        - Train.php 主功能都在这了  请给写入权限
        - cookie 登陆保存的cookie
        - uamtk 登陆成功后获取的用来请求tk值
        - newapptk 获取到的tk值，表单提交都要有tk，如果订单失败可以手动去获取tk -> uamtk()
        - 部分api接口 无视
           
   - 功能支持
        - 自动下单
        - 自动登陆
        - 自动验证登陆状态
        - 查询间隔时间
           
       - 验证码自动识别 请注册诺快（普通用户即可）5块钱可以刷很多验证码了 http://www.ruokuai.com
       
   - 配置参数-有点简陋(o^^o)
       
               // 若快普通账号
               self::$rk_name = '账号';
               self::$rk_password = md5('密码');
       
               // 12306 账号密码
               $this->train_username = '12306账号';
               $this->train_password = '密码';
       
               self::$fromStation = '上海';  // 起始站
               self::$toStation = '广州';  // 终点站
               self::$train_date = '2019-01-15';  // 出发时间
               self::$train_num = 'T169';  // 车次 注意是大写
               self::$train_type = 29;  // 车票类型  all 任意车次 23软卧一等 动卧 28硬卧二等 软座 29硬座 26无座 32商务特等座 30二等座 31一等座 33高级商务
               self::$train_seat = 1;  // 一等座M,特等座P,二等座0,商务座9,硬座1,无座1,软座2,软卧4,硬卧3  // 注意大小写
       
               // 订票个人信息
               self::$my_name = '姓名';
               self::$my_card = '身份证';
               self::$my_phone = '手机号';
       
               self::$sleep = 1000000;  // 微秒  如果为0表示不设置时间限制  安全阀值不知道，自己去体会吧！
       
               $this->toEmail = 'symok@qq.com';  // 接收邮箱
     
   - 声明
        - 本代码只供学习交流使用，务作为商业用途
        - 交流邮箱 symoko@qq.com
           
   - 不错打个赏
        - MD怎么贴图…… 算了先拍片去了![image](https://s2.ax1x.com/2019/01/13/FvrI7d.jpg)
