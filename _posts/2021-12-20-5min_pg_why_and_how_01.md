## 每天5分钟,PG聊通透 - 系列1 - 热门问题 - 链接、驱动、SQL - 第1期 - 为什么数据库链接长时间空闲时有时侯会自动断开?    
                              
### 作者                              
digoal                              
                              
### 日期                              
2021-12-20                            
                              
### 标签                           
PostgreSQL , 热门问题           
                            
----                            
                            
## 背景         
- 问题说明(现象、环境)  
- 分析原因  
- 结论和解决办法  
      
## 链接、驱动、SQL       
      
#### 1、为什么数据库链接长时间空闲时有时侯会自动断开? (长时间空闲, 等待长运行任务)       
https://www.bilibili.com/video/BV1k341147eo/      
```  
链路层是否有设备设置了无数据包传输超时断开会话.  确实没有发包、或者在等待长SQL的执行结果返回.  找到设备配置更大的超时, 或者配置数据库keepalive tcp心跳包的频率.  
其他:  
#statement_timeout = 0                  # in milliseconds, 0 is disabled  
#lock_timeout = 0                       # in milliseconds, 0 is disabled  
#idle_in_transaction_session_timeout = 0        # in milliseconds, 0 is disabled  
#idle_session_timeout = 120000          # in milliseconds, 0 is disabled  
```  
思考题: 哪些情况可能导致数据库链接被自动断开?      
      
  
  
#### [期望 PostgreSQL 增加什么功能?](https://github.com/digoal/blog/issues/76 "269ac3d1c492e938c0191101c7238216")
  
  
#### [PolarDB for PostgreSQL云原生分布式开源数据库](https://github.com/ApsaraDB/PolarDB-for-PostgreSQL "57258f76c37864c6e6d23383d05714ea")
  
  
#### [PostgreSQL 解决方案集合](https://yq.aliyun.com/topic/118 "40cff096e9ed7122c512b35d8561d9c8")
  
  
#### [德哥 / digoal's github - 公益是一辈子的事.](https://github.com/digoal/blog/blob/master/README.md "22709685feb7cab07d30f30387f0a9ae")
  
  
![digoal's wechat](../pic/digoal_weixin.jpg "f7ad92eeba24523fd47a6e1a0e691b59")
  
  
#### [PolarDB 学习图谱: 训练营、培训认证、在线互动实验、解决方案、生态合作、写心得拿奖品](https://www.aliyun.com/database/openpolardb/activity "8642f60e04ed0c814bf9cb9677976bd4")
  
