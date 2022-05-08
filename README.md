# love-home
基于 SSM 爱家房屋租赁管理系统 

这里是 猿码仓库，公众号关注【猿码仓库】。🍅关注公众号【猿码仓库】  简历模板、学习资料、面试题库等都给你💪


`文末获取源码`

`文末获取源码`

`文末获取源码`

@[toc]



# 第17期爱家房屋租赁管理系统


## 展示


[video(video-d8KOxySg-1651213115811)(type-bilibili)(url-https://player.bilibili.com/player.html?aid=298510279)(image-https://img-blog.csdnimg.cn/img_convert/f259c2ec3af66103ea9422c19c241673.png)(title-第17期爱家房屋租赁管理系统ssm)]



![请添加图片描述](https://img-blog.csdnimg.cn/047960e12e9945feb5964b5977d1030d.png)
## 功能介绍

```md
# 1j house

基于ssm的`爱家房屋租赁管理系统`

## 功能介绍

> 房源信息模块：
 
房源信息展示、房源信息更新、房源信息增加、房源信息删除    

> 账户管理模块： 

账户登录、账户绑定、账户管理   

> 租金结算模块： 

每月租金信息、租金交付功能、月租金收入总额统计  

> 爱家房屋租赁合同管理模块： 

爱家房屋租赁合同录入、爱家房屋租赁合同展示、爱家房屋租赁价格修改、爱家房屋租赁合同终止  

> 报障模块： 

租客报账、管理员报障审核、租客报障统计   

> 日程模块：  

收租日程显示

# 项目介绍
## 框架：

项目整体采用spring+springMVC+mybatis框架

## 数据库：

使用mysql数据库

## 服务器：
Tomcat服务器部署
```


![请添加图片描述](https://img-blog.csdnimg.cn/d0766a002fec4ab19baf2e218222dbc7.png)
![请添加图片描述](https://img-blog.csdnimg.cn/a7f4ff82593f41d2aab13f80cb6ea092.png)
```sql
/*
Navicat MySQL Data Transfer

Source Server         : chicken
Source Server Version : 50626
Source Host           : localhost:3306
Source Database       : zu

Target Server Type    : MYSQL
Target Server Version : 50626
File Encoding         : 65001

Date: 7099-10-10 21:56:34
*/

SET FOREIGN_KEY_CHECKS=0;

-- ----------------------------
-- Table structure for apply
-- ----------------------------
DROP TABLE IF EXISTS `apply`;
CREATE TABLE `apply` (
  `apply_id` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) NOT NULL,
  `address` varchar(255) DEFAULT NULL,
  `area` double(255,0) DEFAULT NULL,
  `price` double(10,2) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  `userlist_id` int(255) NOT NULL,
  PRIMARY KEY (`apply_id`,`house_id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of apply
-- ----------------------------

-- ----------------------------
-- Table structure for applyout
-- ----------------------------
DROP TABLE IF EXISTS `applyout`;
CREATE TABLE `applyout` (
  `aoid` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`aoid`)
) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of applyout
-- ----------------------------
INSERT INTO `applyout` VALUES ('3', 'b1', '桃源居', '已拒绝', '10');
INSERT INTO `applyout` VALUES ('6', 'k2', '贝岗街18号', '已拒绝', '15');

-- ----------------------------
-- Table structure for checkout
-- ----------------------------
DROP TABLE IF EXISTS `checkout`;
CREATE TABLE `checkout` (
  `cid` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`cid`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of checkout
-- ----------------------------
INSERT INTO `checkout` VALUES ('2', 'k2', '贝岗街18号', '已退租', '15');
INSERT INTO `checkout` VALUES ('3', 'c1', '广药1-364', '已退租', '10');

-- ----------------------------
-- Table structure for hetong
-- ----------------------------
DROP TABLE IF EXISTS `hetong`;
CREATE TABLE `hetong` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `chuzu` varchar(255) DEFAULT NULL,
  `chuzu_idcard` varchar(255) DEFAULT NULL,
  `zuke` varchar(255) DEFAULT NULL,
  `zuke_idcard` varchar(255) DEFAULT NULL,
  `fromdate` varchar(255) DEFAULT NULL,
  `todate` varchar(255) DEFAULT NULL,
  `price` double(10,2) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `house_id` varchar(255) DEFAULT NULL,
  `payday` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of hetong
-- ----------------------------
INSERT INTO `hetong` VALUES ('5', '张三', '440411199208018201', '李四', '440421199509088888', '2017-09-01', '2018-09-14', '900.00', '菊花园', 'c3', '2');

-- ----------------------------
-- Table structure for houselist
-- ----------------------------
DROP TABLE IF EXISTS `houselist`;
CREATE TABLE `houselist` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `houseid` varchar(255) NOT NULL,
  `address` varchar(255) NOT NULL,
  `area` double DEFAULT NULL,
  `price` double(10,2) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`,`houseid`)
) ENGINE=InnoDB AUTO_INCREMENT=22 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of houselist
-- ----------------------------
INSERT INTO `houselist` VALUES ('16', 'c3', '菊花园1-364', '60', '700.00', '已租赁');
INSERT INTO `houselist` VALUES ('17', 'k1', '东风街13号', '63.2', '1300.00', '已租赁');
INSERT INTO `houselist` VALUES ('20', 'b5', '穗石村18号', '60', '700.00', '未租赁');
INSERT INTO `houselist` VALUES ('21', 'k8', '穗石村1号', '66', '800.00', '未租赁');

-- ----------------------------
-- Table structure for paid
-- ----------------------------
DROP TABLE IF EXISTS `paid`;
CREATE TABLE `paid` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `price` double(10,2) DEFAULT NULL,
  `date` date DEFAULT NULL,
  `paydate` date DEFAULT NULL,
  `name` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of paid
-- ----------------------------
INSERT INTO `paid` VALUES ('5', 'c1', '广药1-364', '500.00', '2017-09-14', '2017-09-27', '赵颖欣', '10', '租金已缴');
INSERT INTO `paid` VALUES ('6', 'c3', '菊花园1-364', '700.00', '2017-09-30', '2017-09-28', '李四', '12', '租金已缴');
INSERT INTO `paid` VALUES ('7', 'c2', '碧桂园1-364', '4365.00', '2017-10-31', '2017-10-08', '张三', '14', '租金已缴');
INSERT INTO `paid` VALUES ('8', 'k2', '贝岗街18号', '700.00', '2017-10-31', '2017-10-10', '张思', '15', '租金已缴');
INSERT INTO `paid` VALUES ('9', 'c1', '广药1-364', '5000.00', '2017-10-31', '2017-10-10', '赵颖欣', '10', '租金已缴');

-- ----------------------------
-- Table structure for schedule
-- ----------------------------
DROP TABLE IF EXISTS `schedule`;
CREATE TABLE `schedule` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `date` varchar(255) DEFAULT NULL,
  `content` text,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of schedule
-- ----------------------------
INSERT INTO `schedule` VALUES ('2', '2017-09-08', '收数');
INSERT INTO `schedule` VALUES ('3', '2017-09-20', '今天是收租日');

-- ----------------------------
-- Table structure for solve
-- ----------------------------
DROP TABLE IF EXISTS `solve`;
CREATE TABLE `solve` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `date` date DEFAULT NULL,
  `detail` text,
  `name` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of solve
-- ----------------------------
INSERT INTO `solve` VALUES ('4', 'c1', '广药1-364', '2017-09-08', 'kk', '赵颖欣', '10', '已处理');
INSERT INTO `solve` VALUES ('5', 'c3', '菊花园1-364', '2017-09-28', '天花板漏水', '李四', '12', '已处理');
INSERT INTO `solve` VALUES ('6', 'c2', '碧桂园1-364', '2017-10-08', '窗户坏了', '张三', '14', '已处理');
INSERT INTO `solve` VALUES ('7', 'k2', '贝岗街18号', '2017-10-10', '天花板漏水', '张思', '15', '已处理');
INSERT INTO `solve` VALUES ('8', 'c1', '广药1-364', '2017-10-09', '空调漏水', '赵颖欣', '10', '已处理');

-- ----------------------------
-- Table structure for topaid
-- ----------------------------
DROP TABLE IF EXISTS `topaid`;
CREATE TABLE `topaid` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `price` double(10,2) DEFAULT NULL,
  `date` date DEFAULT NULL,
  `name` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of topaid
-- ----------------------------

-- ----------------------------
-- Table structure for user
-- ----------------------------
DROP TABLE IF EXISTS `user`;
CREATE TABLE `user` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `username` varchar(255) DEFAULT NULL,
  `password` varchar(255) DEFAULT NULL,
  `type` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of user
-- ----------------------------
INSERT INTO `user` VALUES ('1', 'admin', '123456', 'admin');
INSERT INTO `user` VALUES ('2', '赵颖欣', '12345', 'zuke');
INSERT INTO `user` VALUES ('3', 'zyx', '12345', 'zuke');
INSERT INTO `user` VALUES ('5', 'cwy', '12345', 'zuke');

-- ----------------------------
-- Table structure for userlist
-- ----------------------------
DROP TABLE IF EXISTS `userlist`;
CREATE TABLE `userlist` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `idcard` varchar(255) NOT NULL,
  `phone` varchar(255) DEFAULT NULL,
  `user_id` int(11) NOT NULL,
  PRIMARY KEY (`id`,`idcard`)
) ENGINE=InnoDB AUTO_INCREMENT=17 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of userlist
-- ----------------------------
INSERT INTO `userlist` VALUES ('12', '李四', '440421199509088888', '18826107777', '3');
INSERT INTO `userlist` VALUES ('15', '张思', '441601199312214414', '159192134000', '5');

-- ----------------------------
-- Table structure for wrong
-- ----------------------------
DROP TABLE IF EXISTS `wrong`;
CREATE TABLE `wrong` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `date` date DEFAULT NULL,
  `detail` text,
  `name` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) DEFAULT NULL,
  `status` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of wrong
-- ----------------------------

-- ----------------------------
-- Table structure for zulist
-- ----------------------------
DROP TABLE IF EXISTS `zulist`;
CREATE TABLE `zulist` (
  `zid` int(11) NOT NULL AUTO_INCREMENT,
  `house_id` varchar(255) NOT NULL,
  `price` double(10,2) DEFAULT NULL,
  `address` varchar(255) DEFAULT NULL,
  `userlist_id` int(11) NOT NULL,
  `contract_id` int(11) NOT NULL,
  PRIMARY KEY (`zid`,`house_id`)
) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=utf8;

-- ----------------------------
-- Records of zulist
-- ----------------------------
INSERT INTO `zulist` VALUES ('7', 'c3', '700.00', '菊花园1-364', '12', '5');
SET FOREIGN_KEY_CHECKS=1;

```

## 这里

[猿码仓库](https://mp.weixin.qq.com/s/xJgaC-NudRu0v3wM1yPIwg)




![image](https://tva3.sinaimg.cn/large/007F3CC8ly1h20u91pgl4j31bi0hcafx.jpg)
