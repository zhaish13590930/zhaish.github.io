Mysql学习笔记
1.安装
user:root
pwd:
2:基本命令
	create database | table 
3: charset 
4: enginne

alter database webbase character set utf-8;
ALTER DATABASE `webbase` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
ALTER TABLE `member` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;

mysql优化概览
1.数据库层面
	基础设计更重要.
	表结构是否合理
	是否有正确的索引使查询更加高效
	是否选择了正确是存储引擎,把握了每种存储引擎的优缺点
	是否选择了正确的行格式Row Format
	应用程序是否选择了正确的锁策略
	缓存的已使用内存大小是否合理:足够大能hold住频繁的存取数据,但不要过大超过了物理内存和导致分页,
						主要是InnoDB buffer pool, the MyISAM key cache, and the MySQL query cache.
	
2.硬件层面
	硬盘查找.一次seek低于10ms,一秒大概100次seek.把数据放在多个硬盘上可以优化seek time
	硬盘读写.这个比优化seek time更容易,可以从多张硬盘里并行读.
	cpu周期
	内存大小
3.注释语法
===========================
1.优化SQL语句
	
