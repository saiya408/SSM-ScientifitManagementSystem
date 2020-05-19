# 基于SSM框架组合技术开发的科研管理系统
(毕业设计)使用SSM框架组合技术开发科研管理系统

大学毕业设计，使用SSM组合技术开发一个高校科研管理系统

###### 计划重构为springboot项目（springboot + mybatis） 地址：
<https://github.com/IamDJJ/scientifit-management-system>


## 数据库设计

表设计，用到11个表

1. 用户表：用户(yonghu)
   字段：用户编号(yhid),用户名(yhm),密码(mm),姓名(xm),学院(xy),QQ(QQ),电话(dh),性别(xb),年龄(nl)
2.  管理员表：管理员(gly)
   字段：管理员编号(glyid),用户名(yhm),密码(mm),姓名(xm)
3. 表：合同(hetong)
   字段：合同编号(htid),合同标题(htbt),合同编号(htbh),合同内容(htnr),起草时间(qcsj),起草人(qcr),甲方(jf),甲方联系方式(jflxfs),乙方(yf),乙方联系方式(yflxfs),状态(zt)
4. 表：合同变更(htbg)
   字段：合同变更编号(htbgid),合同编号(htbh),变更说明变更人(bgsmbgr),时间(sj),状态(zt)
5. 表：项目(xiangmu)
   字段：项目编号(xmid),项目名称(xmmc),负责人(fzr),项目阶段(xmjd),概述(gs),立项时间(lxsj),介绍(js),用户(yh),状态(zt)
6. 表：项目变更(xmbg)
   字段：项目变更编号(xmbgid),项目(xm),变更内容(bgnr),项目说明(xmsm)
7. 表：项目中检(xmzj)
   字段：项目中检编号(xmzjid),项目(xm),中检内容(zjnr),用户(yh),时间(sj)
8. 表：项目结项(xmjx)
   字段：项目结项编号(xmjxid),项目(xm),结项说明(jxsm),用户(yh),时间(sj),备注(bz)
9. 表：类型(leixing)
   字段：类型编号(lxid),类型(lx)
10. 表：产权级别(cqjb)
    字段：产权级别编号(cqjbid),级别(jb)
11. 表：知识产权(zscq)
    字段：知识产权编号(zscqid),产权名称(cqmc),类型(lx),附件(fj),内容(nr),产权级别(cqjb),依托成果(ytcg),登记人(djr),登记时间(djsj)



1. 使用者（两个角色权限不同）

1. 用户
2. 系统管理员

1. 注册
2. 登录（分为用户登录和系统管理员登录）

首页

1. 用户个人信息

1. 用户可以修改自己的个人信息，如学院，QQ，电话等
2. 用户可以修改自己的密码（密码需要加密）

1. 横向项目管理

1. 用户进行合同登记和合同变更两个部分
2. 合同登记和变更需要系统管理员审核确定通不通过
3. 用户可以模糊查询自己的横向项目

1. 纵向项目管理

1. 用户可以项目立项，项目变更，项目中检，项目结项等管理
2. 用户项目立项需要得到管理员审核才能确定通过与否
3. 用户可以模糊查询纵向项目

1. 知识产权管理

1. 产权基本信息，产权级别，依托成果等。包括论文、专利、软件著作权、著作、获奖、鉴定成果、成果推广、研究报告、音像、地图等信息录入查询功能。

1. 社科统计

统计系统中的相应的横向项目，纵向项目，知识产权等的统计

1. 系统管理员是可以管理用户和用户所拥有的项目的

-----

2020.5.19

项目更新，由于该项目过于久远，还是使用SSM和jdk1.6实现的。
github出现错误警告了：
Remediation
Upgrade jquery to version 3.5.0 or later.


所以这次重构项目，将其更新为spring boot + jsp + jdk 11，更改为maven管理
重构的好处：
1. 以前的SSM项目，需要tomcat容器承载，需要配置文件配置，看起来太笨重，部署起来也很笨重，完全不轻量化。
2. spring boot的好处，自带tomcat，再也不用担心tomcat配置问题和tomcat版本问题而烦恼了，项目可以不重度依赖配置文件，注解化开发更方便项目维护。
3. maven管理项目，可以更方便的注入依赖包，比如需要什么工具只需要在maven下载，省去很多繁琐的创建依赖过程。

计划重构的项目地址：
<https://github.com/IamDJJ/scientifit-management-system>

