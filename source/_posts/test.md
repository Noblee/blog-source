---
title: test
tags: []
originContent: ''
categories: []
toc: false
date: 2019-02-27 18:48:57
---

春招面试

-   <span class="content mubu-node"
    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">关系数据库复习</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">架构</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">索引</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">锁</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">语法</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">范式</span>
-   <span class="content mubu-node"
    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">如何设计一个关系数据库</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">存储模块（持久化，类似于文件系统）</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">程序实例</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">存储管理</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">页或者块存取</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">缓冲机制</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">时间和空间局部性原理</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">SQL解析模块</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">注意缓存SQL编译结果</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">日志管理</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">权限划分</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">容灾机制</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">索引管理</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">为什么要使用索引？</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">快速查询数据</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">除非在数据量比较小的情况下，否则把全部的信息读入内存进行扫描是一种效率很低的方法，所以要使用索引。</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">什么样的信息能成为索引？</span>
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">主键</span>
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">唯一键</span>
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">普通件等</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">索引的数据结构？</span>
                -   <span class="content mubu-node collapsed"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">平衡二叉树</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">红黑树</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">AVL树</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">由于每个节点都只有两个孩子，一个节点索引太少，故一般不使用。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">B树</span>
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">B+树</span>
                    -   <span class="content mubu-node"
                        images="%5B%7B%22id%22%3A%2212168a38766a311b-2391178%22%2C%22uri%22%3A%22document_image%2Fdebfc666-4b29-4fdf-b1eb-7e54a90cecc1-2391178.jpg%22%2C%22ow%22%3A1335%2C%22oh%22%3A763%7D%5D"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                        <img src="https://img.mubu.com/document_image/debfc666-4b29-4fdf-b1eb-7e54a90cecc1-2391178.jpg" class="attach-img" />
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Hash结构</span>
                    -   <span class="content mubu-node" color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">结构：</span>
                        -   <span class="content mubu-node"
                            images="%5B%7B%22id%22%3A%221168a3a0aec301f-2391178%22%2C%22uri%22%3A%22document_image%2Fb986c8c5-9d5f-4730-b8fc-6a61829fe902-2391178.jpg%22%2C%22ow%22%3A991%2C%22oh%22%3A599%7D%5D"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                            <img src="https://img.mubu.com/document_image/b986c8c5-9d5f-4730-b8fc-6a61829fe902-2391178.jpg" class="attach-img" />
                    -   <span class="content mubu-node" color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">优点</span>
                        -   <span class="content mubu-node"
                            color="#333333"
                            style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">效率更高</span>
                    -   <span class="content mubu-node" color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">缺点</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">仅仅能进行IN，不能使用范围查询</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">不能进行排序操作</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">不能利用部分索引查询（只能全量索引）</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">不能避免表扫描</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">冲突太多的话，效率降低。</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">不是主流索引。</span>
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">BitMap</span>
                    -   <span class="content mubu-node collapsed"
                        color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">结构</span>
                        -   <span class="content mubu-node"
                            color="#333333"
                            images="%5B%7B%22id%22%3A%223b3168a3a5f52b0b9-2391178%22%2C%22uri%22%3A%22document_image%2Ff4c01143-6f73-4d87-9a2f-8a062b456513-2391178.jpg%22%2C%22ow%22%3A869%2C%22oh%22%3A605%7D%5D"
                            style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                            <img src="https://img.mubu.com/document_image/f4c01143-6f73-4d87-9a2f-8a062b456513-2391178.jpg" class="attach-img" />
                    -   <span class="content mubu-node" color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">条件</span>
                        -   <span class="content mubu-node"
                            color="#333333"
                            style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">当表中的某个字段只有几种值时。</span>
                    -   <span class="content mubu-node" color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">缺点</span>
                        -   <span class="content mubu-node"
                            color="#333333"
                            style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">锁的粒度很大，由于增删改查时表的位图的顺序和值可能会改变。</span>
                    -   <span class="content mubu-node" color="#333333"
                        style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">应用</span>
                        -   <span class="content mubu-node"
                            color="#333333"
                            style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">当前只有oracle的数据库支持。不适用于高并发的联机事务处理系统（即OLTP），而适用于并发较少，且统计运算较多的联机分析处理系统（OLAP系统）。</span>
                -   <span class="content mubu-node" color="#dc2d1e"
                    style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">结论</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">B+树的磁盘读写代价更低（节点不存数据）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">B+树的查询效率更加稳定（数据高度相同）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">B+树更有利于对数据库的扫描（有链）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">B+树有利于范围查询（如图）</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">密集索引和稀疏索引的区别？</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">密集索引</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">密集索引文件中的每个搜索码值都对应一个索引值。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">一个表只能有一个密集索引。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">稀疏索引</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">稀疏索引文件只为索引码的某些值建立索引项</span>
                -   <span class="content mubu-node collapsed"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Mysql的索引</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">InnoDB</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">若一个主键被定义，该主键则作为密集索引</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">若没有主键被定义，该表的第一个唯一非空索引则作为密集索引。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">若全部不满足，innoDB内部生成一个隐藏主键（密集索引）。(六字节，随着数据的插入自增)</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">非主键索引（稀疏索引）只储存相关键位及其对应的主键（密集索引）值，存在二次查找。</span>
                            -   <span class="content mubu-node"
                                images="%5B%7B%22id%22%3A%2275168a3bcdd53197-2391178%22%2C%22uri%22%3A%22document_image%2Fdf3ae085-17e9-4678-9539-f620cac02c93-2391178.jpg%22%2C%22ow%22%3A644%2C%22oh%22%3A596%7D%5D"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                                <img src="https://img.mubu.com/document_image/df3ae085-17e9-4678-9539-f620cac02c93-2391178.jpg" class="attach-img" />
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">表文件结构</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">结构文件（.frm）</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">数据文件和索引文件（.ibd）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">MyISAM</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">ISAM（Indexed
                            Sequential Access Method）</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">表文件结构</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">结构文件（.frm）</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">索引文件（.MYI）</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">数据文件（.MYD）</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">如何定位并优化慢查询SQL？</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">根据慢日志定位慢查询SQL。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">show
                        variables like '%quer%'</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">show
                        status like '%slow\_queries%'</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">使用explain等工具分析SQL。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">type字段速度递减表：</span>
                        -   <span class="content mubu-node"
                            images="%5B%7B%22id%22%3A%2231b168a48f807910b-2391178%22%2C%22uri%22%3A%22document_image%2F8a4c197d-3fe0-4c7f-beb7-3aee0716a835-2391178.jpg%22%2C%22ow%22%3A1346%2C%22oh%22%3A124%7D%5D"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                            <img src="https://img.mubu.com/document_image/8a4c197d-3fe0-4c7f-beb7-3aee0716a835-2391178.jpg" class="attach-img" />

                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">index和all都是全表扫描应当优化。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">extra：出现下面两个代表Mysql不能使用索引。应该尽可能的进行优化</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">using
                            filesort </span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">mysql中无法利用索引完成排序操作称为“文件排序”。
                                </span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">表示mysql将对结果使用一个外部索引排序，而不是从表里按索引次序读到相关内容</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">using
                            temporary</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">表示mysql对查询结果使用临时表。常见于order
                                by 和分组查询group by。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">修改SQL或者尽量让SQL走索引。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">修改SQL</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">添加索引：</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">alter
                            table person\_info\_large add index
                            idx\_name(name);</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">何为最左匹配原则?</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">mysql会一直向右匹配直到遇到范围查询（&gt;,&lt;,between,like）就停止匹配，a
                    = 3 and b = 4 and c &gt;5 and d =6
                    如果建立（a,b,c,d）顺序的索引，d的是用不到索引的，如果建立（a,
                    b, d,
                    c）的索引则都可以用到，abc的顺序可以任意排序。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">"="
                    和 “in”
                    可以乱序，mysql的查询优化器会优化索引为可识别的形式。</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">联合索引的最左匹配原则的成因?</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">orderby原则。第一个字段完全有序，第二个字段在第一个字段有序的条件下有序....</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">索引是建立的越多越好吗</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">数据量小的表不需要建立索引，建立会增加额外的索引开销。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">数据变更需要维护索引，因此更多的索引意味着更多的维护成本。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">更多的索引意味着也需要更多的空间。</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">作业：研究引擎mysql的两个</span>
        -   <span class="content mubu-node"
            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">锁模块</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">T锁的分类？</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">粒度划分</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">表级锁</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">行级锁</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">页级锁</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">级别</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">X</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">S</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">加锁方式</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">自动</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">显式</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">操作划分</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">DML锁</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">DDL锁</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">使用方式划分</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">乐观锁</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">乐观锁其实就是没有锁。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">乐观锁
                            = 乐观并发控制</span>
                        -   <span class="content mubu-node"
                            color="#dc2d1e"
                            style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">是一种用来解决写-写冲突的无锁并发控制，认为事务间争用没有那么多，所以先进行修改，在提交事务前，检查一下事务开始后，有没有新提交改变，<span
                            class="bold"
                            style="font-weight: bold;">如果没有就提交，如果有就回滚并重试(</span>乐观并发控制类似自选锁<span
                            class="bold"
                            style="font-weight: bold;">)</span>。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">问题：回滚有可能导致更新丢失。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">自旋锁(spinlock)</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">while
                                (抢锁(lock) == 没抢到) { }</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">乐观并发控制适用于低数据争用，写冲突比较少的环境。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">悲观锁（一直在讲的）</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">先去锁再访问。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">全程用排它锁锁住访问数据。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">加锁开销</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">可能导致死锁</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">T数据库事务的四大特性</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">原子性</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">要么执行，要不全不做</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">一致状性</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">从一个一致状态到另外一个一致状态（一致状态由业务逻辑确定如转账）</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">隔离性</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">一个事务的执行不应该影响其他事务的执行</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">持久性</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">一个事务提交后，他所作出的影响应该永远的保存在数据库中。</span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">T事务隔离级别以及各级别下的并发访问问题？</span>
                -   <span class="content mubu-node"
                    images="%5B%7B%22id%22%3A%2239b168add8eccd0ac-2391178%22%2C%22uri%22%3A%22document_image%2Fc4fe48f8-94e5-40c7-b53e-822c02dd322e-2391178.jpg%22%2C%22ow%22%3A1686%2C%22oh%22%3A704%7D%5D"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">read
                    uncommited(RU) &lt; read commited(RC) &lt; repetable
                    read(RR) &lt; serializable</span>
                    <img src="https://img.mubu.com/document_image/c4fe48f8-94e5-40c7-b53e-822c02dd322e-2391178.jpg" class="attach-img" />

                -   <span class="content mubu-node collapsed"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">1.更新丢失（写-写情况，乐观控制）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在乐观并发控制中，如果事务A执行完后发现已经有其他事务B对并发访问数据进行了提交。事务A在回滚的过程中把事务B提交的更新丢失，并恢复到A开始执行的时候。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">mysql所有事务隔离级别在数据库层面均可避免。</span>
                    -   <span class="content mubu-node"
                        images="%5B%7B%22id%22%3A%2210c168ad9d89ee132-2391178%22%2C%22uri%22%3A%22document_image%2Ff34b48b8-fa22-4a8d-a6f3-5ef6363a218a-2391178.jpg%22%2C%22ow%22%3A1072%2C%22oh%22%3A441%7D%5D"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                        <img src="https://img.mubu.com/document_image/f34b48b8-fa22-4a8d-a6f3-5ef6363a218a-2391178.jpg" class="attach-img" />
                -   <span class="content mubu-node collapsed"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">2.脏读（读-写情况）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在事务还没有提交时就可以对相关字段进行读（read
                        uncommited））。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">设置为read
                        commited（oracle默认的事务隔离级别）以上级别可以避免。</span>
                -   <span class="content mubu-node collapsed"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">3.不可重复读（读-写情况）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">可重复读的隔离界别是指重复读的每一次都是相同的。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在A事务中每次读同一个数据，由于B事务的提交，使A多次读的数据不同导致的问题。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">解决方案；在RR模式下事务A第一次读数据很重要，第一次读是当前读，并建立快照，之后的读都是快照度，即和之前一样。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">repetable-read(RR)（mysql默认的事务隔离级别）以上可以避免，</span>
                    -   <span class="content mubu-node" color="#dc2d1e"
                        style="color: rgb(220, 45, 30); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"><span
                        class="bold"
                        style="font-weight: bold;">即便在"可重复读"可能导致当前读的数据不是当前的值，但如果更新句式使用的是XX=XX+100的这种句式，不会导致更新出错（这是由于update使用的是当前读）。</span></span>
                -   <span class="content mubu-node collapsed"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">4.幻读(幻行)</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在事务A执行了一个当前读操作，事务B在事务A的影响区间内插入/删除了数据，事务A又执行了一个当前读操作出现了“幻行”。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">MySQL可以在RR级别下避免幻读，但这不是理论情况。</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">T两段锁协议</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在一个事务里面，分为加锁(lock)阶段和解锁(unlock)阶段,也即所有的lock操作都在unlock操作之前,</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">为什么需要两阶段加锁？</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">引入2PL是为了保证事务的隔离性，即多个事务在并发的情况下等同于串行的执行。
                        在数学上证明了如下的封锁定理:
                        如果事务是良构的且是两阶段的，那么任何一个合法的调度都是隔离的。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">两阶段加锁对性能的影响</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">工程：MyISAM与InnoDB关于锁方面的区别是什么？</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">MyISAM默认支持表级锁，不支持行级锁</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">InnoDB默认用的是行级锁，也支持表级锁。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">事务自动提交</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">autocommit字段，修改只针对当前session。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">只有在有索引的情况下是行级锁或者gap锁。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">gap锁在普通非唯一索引时使用。//todo</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">其他情况下为表级意向锁。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">IS
                            IX。 todo</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">MyISAM适合的场景</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">频繁执行全表count语句</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对数据进行增删改的频率不高，查询非常频繁。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">没有事务</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">InnoDB</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">数据增删改查都很频繁。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">可靠性比较高，需要事务。</span>
            -   <span class="content mubu-node"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">InnoDB可重复隔离级别下如何避免幻读。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">
                    表象（基于伪MVCC实现的快照读（非堵塞读），在RR和RC情况下）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">当前读</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">读取当前的记录，并且在读的过程中加锁，查询加S锁，其他加X锁。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">select...lock
                            in share mode 、select...for update</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">update</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">delete</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">insert</span>
                        -   <span class="content mubu-node"
                            images="%5B%7B%22id%22%3A%22e7168aedaded7195%22%2C%22uri%22%3A%22document_image%2F0ec84a20-9f62-42ba-b680-79cefa793b37-2391178.jpg%22%2C%22ow%22%3A1156%2C%22oh%22%3A844%7D%5D"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                            <img src="https://img.mubu.com/document_image/0ec84a20-9f62-42ba-b680-79cefa793b37-2391178.jpg" class="attach-img" />
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">快照读</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">select</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在serializable情况下快照读退化为当前读</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">快照读是为了提升并发性能</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">快照读是基于多MVCC版本并发控制</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">可以认为MVCC是行级锁的一个变种，他在很多情况下避免了加锁操作，开销更低，但可能读到历史版本。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在RC情况下快照读和当前读结果相同</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在RR模式下事务A第一次读数据很重要，第一次读是当前读，并建立快照，之后的读都是快照度，即和之前一样。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在RR模式下可以使用当前读（lock
                            in share
                            mode）读到不一样的数据即真是数据。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">内在（next-key锁（行锁+gap锁））</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">行锁</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">gap锁（只有RR和S下才有）</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">gap就是索引记录中插入新记录的空隙。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">gap锁就是锁住一个范围但是不包括记录本身。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">gap锁的目的是为了防止一个事务的两次当前读出现幻读的情况。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">如果where条件全部命中，则不会用gap锁，只会加记录锁。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">如果where条件部分命中或者全不命中，则会加Gap锁。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Gap锁会用在非唯一索引或者不走索引的当前读中。</span>
                            -   <span class="content mubu-node"
                                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span>
            -   <span class="content mubu-node collapsed"
                style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">RC、RR级别下的InnoDB的非堵塞读(快照读)如何实现?（完备）</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">DB\_TRX\_ID</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">标识最近一次对本行记录进行修改的事务id。
                        包括update和delete。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在innoDB中删除操作也不过是修改行中的隐藏位deleted位。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">DB\_ROLL\_PTR</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">回滚指针，指向改行记录的UNDO日志记录。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">DB\_ROW\_ID</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">即行号，包含随着新行号插入而单调递增的行ID。就是之前所提的如果一个表没有主键和唯一键那么innoDB创建唯一键。</span>
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">undo日志</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">当我们对记录进行变更时就会产生undo记录，undo存储的是老版数据，当一个旧的事务需要读取时，需要顺着undo链找到满足其可见性的记录。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">insert
                        undo log</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">只在事务回滚时需要。</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在事务提交后就可以丢弃。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">update
                        undo log</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">delete和update时产生的undo
                            log</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">不仅在回滚时需要而且快照读也需要。只有在当前快照中不存在涉及到这条记录时才可以被删除。</span>
                        -   <span class="content mubu-node"
                            images="%5B%7B%22id%22%3A%22204168aef6230d17f-2391178%22%2C%22uri%22%3A%22document_image%2F11a48c78-f7e5-4720-bda0-49e588401097-2391178.jpg%22%2C%22ow%22%3A1352%2C%22oh%22%3A530%7D%5D"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">当有field2被更改时</span>
                            <img src="https://img.mubu.com/document_image/11a48c78-f7e5-4720-bda0-49e588401097-2391178.jpg" class="attach-img" />

                        -   <span class="content mubu-node"
                            images="%5B%7B%22id%22%3A%221b2168aef862f50be-2391178%22%2C%22uri%22%3A%22document_image%2F8ed5c3bf-d396-436e-a7a9-ba49a14135a1-2391178.jpg%22%2C%22ow%22%3A1252%2C%22oh%22%3A714%7D%5D"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在当前还有事务使用快照读读取该字段，该字段的这调undo记录还没有被删除时，该条记录又被更改。</span>
                            <img src="https://img.mubu.com/document_image/8ed5c3bf-d396-436e-a7a9-ba49a14135a1-2391178.jpg" class="attach-img" />
                -   <span class="content mubu-node"
                    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">read
                    view</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对读取进行可见性判断，当我们进行快照读即select时，根据当前所处的事务进行可见性判断。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">可见性算法：将undo日志中DB\_TRX\_ID取出来与当前事务id进行对比，如果大于或者等于就通过undo指针就取出上一层的undolog直到小于当前事务id为止。（越新的事务的事务id越大）</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">因为readv
                        iew生成时机的不同，造成了RC和RR两种隔离级别的不同可见性，在RR情况下的session在创建事务之后的第一次快照读时创一个快照即read
                        view，将当前快照中活跃的其他事务记录起来，此后每一次快照读都使用这次的readview。在RC情况下，事务的每次快照读都建立一个新的快照。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">读取数据时的非堵塞就是所谓的mvcc，而innoDB的非堵塞读机制实现了仿照班的mvcc。</span>
                    -   <span class="content mubu-node"
                        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">为什么只实现了伪mvcc机制?</span>
                        -   <span class="content mubu-node"
                            style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">mvcc是多版本并发控制，innoDB没有实现多版本并存，undolog的内容只是串行化的结果不属于多版本并存。</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">所谓”两段＂锁的含义是，事务分为两个阶段，第一阶段是获得封锁，也称为扩展阶段，在这个阶段，事务可以申请获得任何数据项上的任何类型的锁，但是不能释放任何锁；第二阶段是释放封锁，也称为收缩阶段，在这个阶段</span>
-   <span class="content mubu-node collapsed"
    style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">常用的SQL语句</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">show
        variable like 'autocommit'</span>
    -   <span class="content mubu-node"
        style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">set
        session transaction isolation level read uncommited</span>
