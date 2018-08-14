# ipdatabase
二叉树快速搜索IP地址数据库

# 数据
数据源采用2015年广告协会制定的IP地址标准数据库，中国互联网广告行业统一采用的标准IP库。

# 原理
利用二叉树实现IP查询，首先将10进制IPV4地址转化为二进制构建二叉树，利用二叉树搜索进行搜索，查询时间复杂度log2n，比传统IP库n的查询速度高出一个量级。

# 接口
根据IP查询城市或地区的接口是IpHelper类中的findRegionByIp接口，说明如下：

```
/**
 * 静态方法，传入ip地址，返回ip地址所在城市或地区
 * @param ip    IP地址，例：58.30.15.255
 * @return  返回IP地址所在城市或地区，例：北京市
 */
public static String findRegionByIp(String ip)
```

# example
```
public void example() throws Exception {
    String ip = "58.30.15.255";
    String region = IpHelper.findRegionByIp(ip);
    System.out.println(region);
}
```