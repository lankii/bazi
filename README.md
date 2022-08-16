# 简介

- bazi.py 八字排盘，能比常用的排盘更清晰地显示冲、合、刑等关系，计算五行分数，附加《三命通会》等命理评判
- luohou.py 计算罗喉日时,用于提示风水师何时慎用罗盘。
- shengxiao.py 用户生肖合婚等。

软件部署定制技术支持及批八字：微信或钉钉pythontesting


# 安装
- 安裝依赖库

```python
pip install  sxtwl bidict
```

- linux打开终端或windows打开cmd或git的bash或powercmd等工具

进入到代码所在目录。


# 使用

- 生肖合婚

```python
$ python shengxiao.py 虎
你的生肖是： 虎
你的年支是： 寅
================================================================================
合生肖是合八字的一小部分，有一定参考意义，但是不是全部。
合婚请以八字为准，技术支持：钉钉或微信pythontesting
以下为相合的生肖：
================================================================================

与你三合的生肖：马狗
与你六合的生肖：猪
与你三会的生肖：兔龙
================================================================================
以下为不合的生肖：
================================================================================

与你相冲的生肖：猴
你刑的生肖：蛇
被你刑的生肖：猴
与你相害的生肖：蛇
与你相破的生肖：猪
================================================================================
如果生肖同时在你的合与不合中，则做加减即可。
比如猪对于虎，有一个相破，有一六合，抵消就为平性。

```


- 计算罗喉日时

```python
$ python luohou.py 
公历:2021年3月23日	农历:2021年二月十一日   	辛丑-辛卯-庚午	杀师时:卯5-7申15-17
公历:2021年3月24日	农历:2021年二月十二日   	辛丑-辛卯-辛未	杀师时:午11-13辰7-9
公历:2021年3月25日	农历:2021年二月十三日   	辛丑-辛卯-壬申	杀师时:戌19-21丑1-3
公历:2021年3月26日	农历:2021年二月十四日   	辛丑-辛卯-癸酉	杀师时:子23-1午11-13
公历:2021年3月27日	农历:2021年二月十五日   	辛丑-辛卯-甲戌	杀师时:卯5-7午11-13 	年猴:丑年甲戌日 
...
```


- 八字排盘

```python

$ python bazi.py -h
usage: bazi.py [-h] [-b] [-g] [-r] [-n] [--version] year month day time

positional arguments:
  year        year
  month       month
  day         day
  time        time

optional arguments:
  -h, --help  show this help message and exit
  -b          直接输入八字
  -g          是否采用公历
  -r          是否为闰月，仅仅使用于农历
  -n          是否为女，默认为男
  --version   show program's version number and exit


# -- 左宗棠八字

 python bazi.py 1812 11 10 4 -g

日期:
======================================
公历:   1812年11月10日
农历:   1812年十月初七日 穿=害
------------------------------------------------------------------------------------------------------------------------
排盘源码: http://t.cn/E6zzQYj           解读:钉钉或微信pythontesting            墓库： {辰: 水土, 戌: 火, 丑: 金, 未: 木}
甲己-中正土  乙庚-仁义金  丙辛-威制水  丁壬-淫慝木  戊癸-无情火   三会: {亥子丑: 水, 寅卯辰: 木, 巳午未: 火, 申酉戌: 金}
========================================================================================================================
壬 辛 丙 庚            杀 财 己 才
申 亥 午 寅            才 杀 劫 枭            空亡: ('寅', '卯')
------------------------------------------------------------------------------------------------------------------------
　　　　【年】　　　　　　　　　　　【月】　　　　　　　　　　　　【日】　　　　　　　　　　　　【时】　　　　　　
------------------------------------------------------------------------------------------------------------------------
壬＋水【杀】冲丙 -5　　　　　　　辛－金【财】合丙 -3　　　　　　　丙＋火【天】合辛冲壬 6　　　　　　庚＋金【才】 -1　　　　　　　　　
申＋病【长】 -2　　　　　　　　　亥－绝【沐】 -5　　　　　　　　　午＋帝 6　　　　　　　　　　　　　寅＋长【绝】空 3　　　　　　　　　
戊土食　壬水杀　庚金才　　　　　　甲木枭　壬水杀　　　　　　　　　　己土伤　丁火劫　　　　　　　　　　戊土食　丙火比　甲木枭　　　　　　
冲　　　　　　　　　　　　　　　　六合：寅　暗合　　　　　　　　　　合：寅　暗合　　　　　　　　　　　冲　被刑：申　合：午　六合：亥　　
害：亥　　　　　　　　　　　　　　害：申　破：寅　　　　　　　　　　　　　　　　　　　　　　　　　　　破：亥　　　　　　　　　　　　　　
剑锋金　　　　　　　　　　　　　　钗钏金－亡　　　　　　　　　　　　天河水　　　　　　　　　　　　　　松柏木　　　　　　　　　　　　　　


大运
========================================================================================================================
9        壬子   杀:壬＋冲丙　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 会:亥  冲:午  合:申
    1821 辛巳   财:辛－合丙　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  害:寅  会:午
    1822 壬午   杀:壬＋冲丙　　　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 暗合:亥  合:寅  刑:午  冲:子  被刑:午
    1823 癸未   官:癸－　　　　　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥  害:子
    1824 甲申   枭:甲＋冲庚　　　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  合:子  刑:寅
    1825 乙酉   印:乙－合庚冲辛　　　酉－死 - 辛金财　　　　　　　　　　　　 破:子  会:申
    1826 丙戌   比:丙＋合辛冲壬　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 合:午  会:申  合:寅
    1827 丁亥   劫:丁－合壬　　　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  被刑:亥  会:子  破:寅  六合:寅
    1828 戊子   食:戊＋　　　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 会:亥  冲:午  合:申
    1829 己丑   伤:己－　　　　　　　丑－养 - 辛金财　癸水官　己土伤　　　　 六合:子  会:亥  会:子  害:午  暗合:寅
    1830 庚寅   才:庚＋　　　　　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  破:亥  六合:亥  合:午  被刑:申
19       癸丑   官:癸－　　　　　　　丑－养 - 辛金财　癸水官　己土伤　　　　 会:亥  暗合:寅  害:午
    1831 辛卯   财:辛－合丙　　　　空卯－沐 - 乙木印　　　　　　　　　　　　 会:寅  合:亥  暗合:申  破:午
    1832 壬辰   杀:壬＋冲丙　　　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 破:丑  会:寅  合:申  暗合:丑
    1833 癸巳   官:癸－　　　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  合:丑  害:寅  会:午
    1834 甲午   枭:甲＋冲庚　　　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 暗合:亥  合:寅  刑:午  被刑:午  害:丑
    1835 乙未   印:乙－合庚冲辛　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 刑:丑  六合:午  合:亥  冲:丑  会:午  暗合:丑
    1836 丙申   比:丙＋合辛冲壬　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  刑:寅
    1837 丁酉   劫:丁－合壬冲癸　　　酉－死 - 辛金财　　　　　　　　　　　　 合:丑  会:申
    1838 戊戌   食:戊＋合癸　　　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 会:申  合:寅  合:午  暗合:丑  被刑:丑
    1839 己亥   伤:己－　　　　　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  被刑:亥  破:寅  六合:寅  会:丑
    1840 庚子   才:庚＋　　　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 合:申  六合:丑  会:亥  冲:午  会:丑
29       甲寅   枭:甲＋冲庚　　　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  破:亥  六合:亥  合:午  被刑:申
    1841 辛丑   财:辛－合丙　　　　　丑－养 - 辛金财　癸水官　己土伤　　　　 会:亥  暗合:寅  害:午
    1842 壬寅   杀:壬＋冲丙　　　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  破:亥  六合:亥  合:午  被刑:申
    1843 癸卯   官:癸－　　　　　　空卯－沐 - 乙木印　　　　　　　　　　　　 会:寅  合:亥  暗合:申  破:午
    1844 甲辰   枭:甲＋冲庚　　　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 会:寅  合:申
    1845 乙巳   印:乙－合庚冲辛　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  害:寅  会:午
    1846 丙午   比:丙＋合辛冲壬　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 刑:午  被刑:午  合:寅  暗合:亥
    1847 丁未   劫:丁－合壬　　　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥
    1848 戊申   食:戊＋　　　　　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  刑:寅
    1849 己酉   伤:己－合甲　　　　　酉－死 - 辛金财　　　　　　　　　　　　 会:申
    1850 庚戌   才:庚＋冲甲　　　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 合:午  会:申  合:寅
39       乙卯   印:乙－合庚冲辛　　空卯－沐 - 乙木印　　　　　　　　　　　　 会:寅  合:亥  暗合:申  破:午
    1851 辛亥   财:辛－合丙冲乙　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  合:卯  害:申  暗合:午  被刑:亥  破:寅  六合:寅
    1852 壬子   杀:壬＋冲丙　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 被刑:卯  刑:卯  合:申  会:亥  冲:午
    1853 癸丑   官:癸－　　　　　　　丑－养 - 辛金财　癸水官　己土伤　　　　 会:亥  暗合:寅  害:午
    1854 甲寅   枭:甲＋冲庚　　　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  破:亥  六合:亥  合:午  会:卯  被刑:申
    1855 乙卯   印:乙－合庚冲辛　　空卯－沐 - 乙木印　　　　　　　　　　　　 会:寅  合:亥  暗合:申  破:午
    1856 丙辰   比:丙＋合辛冲壬　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 会:卯  害:卯  会:寅  合:申
    1857 丁巳   劫:丁－合壬　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  害:寅  会:午
    1858 戊午   食:戊＋　　　　　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 破:卯  暗合:亥  合:寅  刑:午  被刑:午
    1859 己未   伤:己－　　　　　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥  合:卯
    1860 庚申   才:庚＋合乙　　　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  暗合:卯  刑:寅
49       丙辰   比:丙＋合辛冲壬　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 会:寅  合:申
    1861 辛酉   财:辛－合丙　　　　　酉－死 - 辛金财　　　　　　　　　　　　 六合:辰  会:申
    1862 壬戌   杀:壬＋冲丙　　　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 冲:辰  合:午  会:申  合:寅
    1863 癸亥   官:癸－　　　　　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  被刑:亥  破:寅  六合:寅
    1864 甲子   枭:甲＋冲庚　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 会:亥  冲:午  合:申  合:辰
    1865 乙丑   印:乙－合庚冲辛　　　丑－养 - 辛金财　癸水官　己土伤　　　　 会:亥  破:辰  暗合:寅  害:午
    1866 丙寅   比:丙＋合辛冲壬　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  会:辰  破:亥  六合:亥  合:午  被刑:申
    1867 丁卯   劫:丁－合壬　　　　空卯－沐 - 乙木印　　　　　　　　　　　　 会:辰  合:亥  暗合:申  破:午  会:寅  害:辰
    1868 戊辰   食:戊＋　　　　　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 刑:辰  会:寅  合:申  被刑:辰
    1869 己巳   伤:己－　　　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  害:寅  会:午
    1870 庚午   才:庚＋　　　　　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 刑:午  被刑:午  合:寅  暗合:亥
59       丁巳   劫:丁－合壬　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  害:寅  会:午
    1871 辛未   财:辛－合丙　　　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥  会:巳
    1872 壬申   杀:壬＋合丁冲丙　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 六合:巳  破:巳  被刑:巳  冲:寅  刑:寅  害:亥
    1873 癸酉   官:癸－冲丁　　　　　酉－死 - 辛金财　　　　　　　　　　　　 暗合:巳  会:申  合:巳
    1874 甲戌   枭:甲＋冲庚　　　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 合:午  会:申  合:寅
    1875 乙亥   印:乙－合庚冲辛　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  被刑:亥  破:寅  冲:巳  六合:寅
    1876 丙子   比:丙＋合辛冲壬　　　子＋胎 - 癸水官　　　　　　　　　　　　 会:亥  冲:午  合:申
    1877 丁丑   劫:丁－合壬　　　　　丑－养 - 辛金财　癸水官　己土伤　　　　 会:亥  暗合:寅  合:巳  害:午
    1878 戊寅   食:戊＋　　　　　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  破:亥  六合:亥  合:午  刑:巳  被刑:申  害:巳
    1879 己卯   伤:己－　　　　　　空卯－沐 - 乙木印　　　　　　　　　　　　 会:寅  合:亥  暗合:申  破:午
    1880 庚辰   才:庚＋　　　　　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 会:寅  合:申
69       戊午   食:戊＋　　　　　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 刑:午  被刑:午  合:寅  暗合:亥
    1881 辛巳   财:辛－合丙　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  害:寅  会:午
    1882 壬午   杀:壬＋冲丙　　　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 刑:午  被刑:午  合:寅  暗合:亥
    1883 癸未   官:癸－合戊　　　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥
    1884 甲申   枭:甲＋冲庚　　　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  刑:寅
    1885 乙酉   印:乙－合庚冲辛　　　酉－死 - 辛金财　　　　　　　　　　　　 会:申
    1886 丙戌   比:丙＋合辛冲壬　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 合:午  会:申  合:寅
    1887 丁亥   劫:丁－合壬　　　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  被刑:亥  破:寅  六合:寅
    1888 戊子   食:戊＋　　　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 会:亥  冲:午  合:申
    1889 己丑   伤:己－　　　　　　　丑－养 - 辛金财　癸水官　己土伤　　　　 会:亥  暗合:寅  害:午
    1890 庚寅   才:庚＋　　　　　　空寅＋长 - 戊土食　丙火比　甲木枭　　　　 冲:申  破:亥  六合:亥  合:午  被刑:申
79       己未   伤:己－　　　　　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥
    1891 辛卯   财:辛－合丙　　　　空卯－沐 - 乙木印　　　　　　　　　　　　 合:亥  破:午  暗合:申  合:未  会:寅
    1892 壬辰   杀:壬＋冲丙　　　　　辰＋冠 - 癸水官　乙木印　戊土食　　　　 会:寅  合:申
    1893 癸巳   官:癸－　　　　　　　巳－建 - 庚金才　戊土食　丙火比　　　　 冲:亥  刑:申  破:申  被刑:寅  六合:申  会:未  害:寅  会:午
    1894 甲午   枭:甲＋合己冲庚　　　午＋帝 - 己土伤　丁火劫　　　　　　　　 暗合:亥  合:寅  刑:午  被刑:午  六合:未  会:未
    1895 乙未   印:乙－合庚冲辛　　　未－衰 - 乙木印　丁火劫　己土伤　　　　 会:午  六合:午  合:亥
    1896 丙申   比:丙＋合辛冲壬　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  刑:寅
    1897 丁酉   劫:丁－合壬　　　　　酉－死 - 辛金财　　　　　　　　　　　　 会:申
    1898 戊戌   食:戊＋　　　　　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 会:申  合:寅  合:午  破:未  刑:未
    1899 己亥   伤:己－　　　　　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  合:未  被刑:亥  破:寅  六合:寅
    1900 庚子   才:庚＋　　　　　　　子＋胎 - 癸水官　　　　　　　　　　　　 会:亥  冲:午  害:未  合:申
89       庚申   才:庚＋　　　　　　　申＋病 - 戊土食　壬水杀　庚金才　　　　 害:亥  冲:寅  刑:寅
99       辛酉   财:辛－合丙　　　　　酉－死 - 辛金财　　　　　　　　　　　　 会:申
109      壬戌   杀:壬＋冲丙　　　　　戌＋墓 - 丁火劫　辛金财　戊土食　　　　 合:午  会:申  合:寅
119      癸亥   官:癸－　　　　　　　亥－绝 - 甲木枭　壬水杀　　　　　　　　 刑:亥  害:申  暗合:午  被刑:亥  破:寅  六合:寅
9.0
星宿 ('危', '') ('危', '吉事不取的日子。 宜：入殓、破土、火化、进塔、安葬。 忌：入宅嫁娶诸吉事。')
========================================================================================================================
{'申子辰': '水 寅', '巳酉丑': '金 亥', '寅午戌': '火 申', '亥卯未': '木 巳'} 生：寅申巳亥 败：子午卯酉　库：辰戌丑未
地支六合: {'子丑': '土', '寅亥': '木', '卯戌': '火', '酉辰': '金', '申巳': '水', '未午': '土'}
格局: 杀         | 玉堂贵人： 亥 大败马 ('壬', '申')
学堂: 寅


------------------------------------------------------------------------------------------------------------------------
五行分数 {'金': 15, '木': 11, '水': 17, '火': 12, '土': 5}   八字强弱： 23 通常>29为强，需要参考月份、坐支等 weak: False
湿度分数 -6 正为暖燥，负为寒湿，正常区间[-6,6]
甲[枭]-11   乙[印]-0   丙[比]-7   丁[劫]-5   戊[食]-2   己[伤]-3   庚[才]-10   辛[财]-5   壬[杀]-17   癸[官]-0
------------------------------------------------------------------------------------------------------------------------
出身: 一般
财少身强，柱有比劫，不为福

杀(偏官)分析 **** 喜:身旺  印绶  合煞  食制 羊刃  比  逢煞看印及刃  以食为引   忌：身弱  财星  正官  刑冲  入墓
一曰偏官 二曰七煞 三曰五鬼 四曰将星 五曰孤极星 原有制伏,煞出为福,原无制伏,煞出为祸   性情如虎，急躁如风,尤其是七杀为丙、丁火时。
坐长生、临官、帝旺,更多带比同类相扶,则能化鬼为官,化煞为权,行运引至印乡,必发富贵。倘岁运再遇煞地,祸不旋踵。
七杀喜酒色而偏争好斗、爱轩昂而扶弱欺强
======================================
逢煞看财,如身强煞弱,有财星则吉,身弱煞强,有财引鬼盗气,非贫则夭;
有阳刃配合,即《经》云:煞无刃不显,逢煞看刃是也。
七煞重逢
七煞遇长生乙位，女招贵夫。

------------------------------------------------------------------------------------------------------------------------
子：壬 -- 长 建 胎 [病]           女：癸 -- 死 帝 绝 [沐]           对象：辛 -- 帝 [沐] 病 胎          情人：庚 -- 建 [病] 沐 绝
父：庚 -- 建 [病] 沐 绝           母：乙 -- 胎 [死] 长 帝           兄弟：丙 -- 病 [绝] 帝 长          姐妹：丁 -- 沐 [胎] 建 死
------------------------------------------------------------------------------------------------------------------------
========================================================================================================================
你属: 丙 特点：-- 电 冶 禄巳 火无西向

年份: 申 特点：-- 名都 帝王所居；申宫壬水生 亥时，乃地天交泰


羊刃: 丙 午
======================参考：https://www.jianshu.com/p/c503f7b3ed04
羊刃重重又见禄，富贵饶金玉。 官、印相助福相资。
文星贵人:  丙 申


五行缺土的建议参见 http://t.cn/E6zwOMq


命
=========================

    六丙日生时庚寅，学堂生气助其身；运中有合通金局，必是荣华富贵人。
    丙日庚寅时，生气学堂，丙寅上长生，文章秀气；丙以庚辛为财，寅上庚绝丙旺。若通月气金局者财旺，富贵双全，喜西方运；不通局者财薄。

    丙庚相合遇寅时，险难消除福自随；运至寒门名将相，时来平步上云梯。
    丙日庚寅时准，双亲衰旺离乡。妻儿早害晚荣昌，白虎归山正旺。木有成林松柏，生涯广聚财粮。堆金积玉满高堂，共羡人言上样。

    丙子日庚寅时,生子月,近贵。癸酉月,行水木运,高贵;火木运,五品以上贵。未申、癸午年月,身居武职,大贵,寿浅。

    丙寅日庚寅时,贵不久。生酉申年月,世裔冷职。子丑寅未,贵显。纯寅尤吉。

    丙辰日庚寅时,生寅午戌未年月,妻贤子孝,富贵双全。申子,行北运,大贵。酉丑,富。

    丙午日庚寅时,年月无壬癸子未巳字,飞天禄马,贵。巳酉丑申,主文学,不贵即富。未月,伤官。辰月,先贫后富。亥月,行西运,贵显。

    丙申日庚寅时,亥卯未、申子辰二局,官印两旺,大贵。巳丑财局,吉。寅午戌火局,平。

    丙戌日庚寅时,生亥子月,贵显。申酉年月,行北方运; 寅午戌,行官鬼运,俱大贵。若运临死绝,即入黄泉无疑。

======================================
阴杀:话少,性格柔和
男:因女致祸、因色致祸; 女:赔货


```


-- 鸣谢：本程序的日历使用库　https://pypi.org/project/sxtwl/。
