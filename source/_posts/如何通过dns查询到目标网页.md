---
title: 如何通过dns查询到目标网页
date: 2021-05-24
---

* 域名的层次结构

  以www.example.com为例子说明域名的层级结构。其中的.com部分叫做顶级域名(top-level domain)，.example部分为次级域名，www为主机部分。实际上在顶级域名之上还有一个层级叫做根域名root，因为完整的域名应该如下图所示：

  ```markdown
  主机.次级域名.顶级域名.根域名
  hostname.sld.tld.root
  www.example.www.root
  
  ```

  现有的根域名，是由一个叫做 [ICANN](https://www.icann.org/) （Internet Corporation for Assigned Names and Numbers）的组织管理，总部在美国。

  ```markdown
   这个组织维护这13个根域名列表。早期的 DNS 查询结果是一个512字节的 UDP 数据包。这个包最多可以容纳13个服务器的地址，因此就规定全世界有13个根域名服务器，编号从a.root-servers.net一直到m.root-servers.net。这13台根域名服务器由12个组织独立运营。其中，Verisign 公司管理两台根域名服务器：A 和 J。每家公司为了保证根域名服务器的可用性，会部署多个节点，比如单单 Verisign 一家公司就部署了104台根域名服务器（2016年1月数据）。所以，根域名服务器其实[不止13台](https://www.icann.org/news/blog/there-are-not-13-root-servers)。据统计，截止2016年1月，全世界共有 517 台根域名服务器。你可以在 http://root-servers.org 这个网站查到所有根域名服务器的信息。根域名服务器虽然有域名，但是最少必须知道一台的 IP 地址，否则就会陷入循环查询。一般来说，本机都保存一份根域名服务器的 IP 地址的缓存，叫做 [name.cache](https://www.internic.net/zones/named.cache) 文件
  
  由于根域名是固定的，因此，在日常的域名书写中省去了根域名部分：www.example.www

* 域名是如何查询的

  根据域名的层级结构特性，在本地dns服务区默认保存根域名服务器的地址，从根域名开始，采用自上而下的分层查询方法，逐级查询最终得到目标网页。

  ```markdown
  查询根域名列表，得到顶级域名服务器的NS记录和A记录   (ip地址)
  查询顶级域名服务器，得到次级域名服务器的NS记录和A记录 (ip地址)
  查询次级域名服务器地址，得到最终主机的Ip地址
  
  每个层级域名都有自己的NS记录，这些记录指向本级的域名服务器，本级的域名服务器保存着下一级域名的NS记录，如此，就形成了一个链表式的查询路径。
  层级域名 -> 本级NS记录->本级域名服务器->下一级域名的NS记录->本级域名服务器
  ```

  

