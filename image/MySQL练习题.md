# [MySQL练习题](https://www.cnblogs.com/wupeiqi/articles/5729934.html)

### MySQL测试题

**一、表关系**

请创建如下表，并创建相关约束

![img](E:/BlogFlie/image/425762-20160803224643778-2071849037.png)

**二、操作表**

<font color='red'>1、自行创建测试数据</font>

>```mysql
># 生物表
>	create table class (
>    	cid int AUTO_INCREMENT PRIMARY KEY,
>        caption char(6)
>    )engine=innodb default charset=utf8;
>    
> # 学生表
> 	create table student(
>        sid int AUTO_INCREMENT PRIMARY KEY,
>        sname char(6),
>        gender char(3),
>        class_id int,
>        constraint fk_class_id FOREIGN KEY (class_id) REFERENCES class(cid)
>    )engine=innodb default charset=utf8;
>    
> # 老师表
> 	create table teacher(
>    	tid int AUTO_INCREMENT PRIMARY KEY,
>        tname char(6),
>    )engine=innodb default charset=utf8;
> 
> # 课程表
> 	create table course(
>    	cid int AUTO_INCREMENT PRIMARY KEY,
>        cname char(8),
>        teacher_id int,
>        constraint fk_tea_id FOREIGN KEY (teacher_id) REFERENCES teacher(tid)
>    )engine=innodb default charset=utf8;
>    
> # 成绩表
> 	create table score(
>    	sid int AUTO_INCREMENT PRIMARY KEY,
>        student_id int,
>        teacher_id int,
>        # 将score表中的student_id ，teacher_id多列联合唯一
>        unique uq_sid_tid(student_id, teacher_id)
>    )engine=innodb default charset=utf8;
>    
>```
>
>

<font color='red'>2、查询“生物”课程比“物理”课程成绩高的所有学生的学号；</font>

>```mysql
>select student_id, courese_id FROM score WHERE student_id
>```
>
>

3、查询平均成绩大于60分的同学的学号和平均成绩； 

4、查询所有同学的学号、姓名、选课数、总成绩；

5、查询姓“李”的老师的个数；

6、查询没学过“叶平”老师课的同学的学号、姓名；

7、查询学过“001”并且也学过编号“002”课程的同学的学号、姓名；

8、查询学过“叶平”老师所教的所有课的同学的学号、姓名；

9、查询课程编号“002”的成绩比课程编号“001”课程低的所有同学的学号、姓名；

10、查询有课程成绩小于60分的同学的学号、姓名；

11、查询没有学全所有课的同学的学号、姓名；

12、查询至少有一门课与学号为“001”的同学所学相同的同学的学号和姓名；

13、查询至少学过学号为“001”同学所选课程中任意一门课的**其他同学**学号和姓名；

14、查询和“002”号的同学学习的课程完全相同的其他同学学号和姓名；

15、删除学习“叶平”老师课的SC表记录；

16、向SC表中插入一些记录，这些记录要求符合以下条件：①没有上过编号“002”课程的同学学号；②插入“002”号课程的平均成绩； 

17、按平均成绩从低到高显示所有学生的“语文”、“数学”、“英语”三门的课程成绩，按如下形式显示： 学生ID,语文,数学,英语,有效课程数,有效平均分；

18、查询各科成绩最高和最低的分：以如下形式显示：课程ID，最高分，最低分；

19、按各科平均成绩从低到高和及格率的百分数从高到低顺序；

20、课程平均分从高到低显示（现实任课老师）；

21、查询各科成绩前三名的记录:(不考虑成绩并列情况) 

22、查询每门课程被选修的学生数；

23、查询出只选修了一门课程的全部学生的学号和姓名；

24、查询男生、女生的人数；

25、查询姓“张”的学生名单；

26、查询同名同姓学生名单，并统计同名人数；

27、查询每门课程的平均成绩，结果按平均成绩升序排列，平均成绩相同时，按课程号降序排列；

28、查询平均成绩大于85的所有学生的学号、姓名和平均成绩；

29、查询课程名称为“数学”，且分数低于60的学生姓名和分数；

30、查询课程编号为003且课程成绩在80分以上的学生的学号和姓名； 

31、求选了课程的学生人数

32、查询选修“杨艳”老师所授课程的学生中，成绩最高的学生姓名及其成绩；

33、查询各个课程及相应的选修人数；

34、查询不同课程但成绩相同的学生的学号、课程号、学生成绩；

35、查询每门课程成绩最好的前两名；

36、检索至少选修两门课程的学生学号；

37、查询全部学生都选修的课程的课程号和课程名；

38、查询没学过“叶平”老师讲授的任一门课程的学生姓名；

39、查询两门以上不及格课程的同学的学号及其平均成绩；

40、检索“004”课程分数小于60，按分数降序排列的同学学号；

41、删除“002”同学的“001”课程的成绩；

 