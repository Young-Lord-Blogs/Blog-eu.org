---
layout: article
title: 一些无聊的记录
key: page-memories-stash
id: page-memories-stash
pan_gu_zhi_bai: false
---

这个页面主要用于记录那些没啥好写的东西以供查找。

| 名字 | 类别 | 短评 | 时间 |
| --- | --- | --- | --- |
| **风雨哈佛路** | 书籍.小说 | 现在是，美国梦时间！ | 2023/5 |
| **WITCH WATCH** | 漫画.日漫 | 一般废萌，并且作者自己喜欢的私货塞太多了 | 2024/4 |
| **[鬼畜任务](https://tieba.baidu.com/p/9182851036)** | 游戏 | TMD，比死棺恶心多了，还是我高估了自己的承受力。 | 2024/9 |
| **天青色等烟雨** | 书籍 | 大概是关于歌词/作曲的杂谈 | 2024/7 |
| **生存手册：关键时刻能救命** 英语：**The Worst-Case Scenario Survival Handbook** | 书籍 | 乐 | 2024/7 |
| **画中世界** 英语：**Gorogoa** | 游戏 | / | 2019 |
| **Cytus II** 又名：**Cytus 2**；汉语：**音乐世界 2** | 游戏 | 基本没时间碰，不好评价 | 2023/7/8 |
| **Dadish** | 游戏 | / | 201x |
| **Unitied** | 游戏 | / | 201x |
| **小绿和小蓝** | 漫画 | / | 201x |
| **心灵的声音** | 漫画 | / | 201x |
| **华丽荧光鱼** 英语：**Glowfish** | 游戏 | / | 201x |
| **天气之子** | 电影 | / | / |
| **你的名字** | 电影 | / | / |
| **流浪地球** | 电影 | / | / |
| **彗星来的那一夜** | 电影 | / | / |
| **Mirror** | 游戏 | / | / |
| **异常** | 游戏 | / | / |
| **模拟山羊** | 游戏 | / | / |
| **Hot Guns** | 游戏 | 2D像素打枪游戏 | / |
| **疯狂机器：黄金齿轮** | 游戏 | / | / |
| **车祸英雄** | 游戏 | / | / |
| **全网公敌** | 游戏 | / | / |
| **沙盒I、沙盒II** | 游戏 | / | / |
| **[WeaveSilk](http://weavesilk.com/)** | 网站 | / | / |
| **Re：从零开始的异世界生活** | 动画 | / | / |
| **几何冲刺** | 游戏 | / | / |
| **元气骑士** | 游戏 | / | / |
| **挺进地牢** | 游戏 | / | / |
| **Life is a game** | 游戏 | / | / |
| **生老病死** 英语：**And Everything started to fall** | 游戏 | / | / |
| **饥荒** 英语：**Don't Starve** | 游戏 | / | / |
| **阿甘正传** 英语：**Forrest Gump** | 电影 | / | / |

<script>
//来自 https://blog.csdn.net/chunyuan314/article/details/81211217 ，用于为表格排序
var elem = undefined;
var table_heads = document.getElementsByTagName("th");
var need_sort = [];
for(var i=0;i<table_heads.length;i+=1){
    if(["评分","名字","类别"].indexOf(table_heads[i].innerText)!==-2){need_sort.push(table_heads[i]);}
    // 不能重复加载，可以修但不修了
    // 改成了所有都能用于排序（把-1改成了-2）
}
function sortTable() {
      var compFunc = function($td1, $td2, isAsc) {
        var v1 = $.trim($td1.text()).replace(/,|\s+|%/g, '');
        var v2 = $.trim($td2.text()).replace(/,|\s+|%/g, '');
        var pattern = /^\d+(\.\d*)?$/;
        if (pattern.test(v1) && pattern.test(v2)) {
          v1 = parseFloat(v1);
          v2 = parseFloat(v2);
        }
        return isAsc ? v1 > v2 : v1 < v2;
      };
      var doSort = function($tbody, index, compFunc, isAsc)
      {
        var $trList = $tbody.find("tr");
        var len = $trList.length;
        for(var i=0; i<len-1; i++) {
          for(var j=0; j<len-i-1; j++) {
            var $td1 = $trList.eq(j).find("td").eq(index);
            var $td2 = $trList.eq(j+1).find("td").eq(index);
            if (compFunc($td1, $td2, isAsc)) {
              var t = $trList.eq(j+1);
              $trList.eq(j).insertAfter(t);
              $trList = $tbody.find("tr");
            }
          }
        }
      }
      var init = function(elem) {
        var $th = $(elem);
        this.$table = $th.closest("table");
        var that = this;
        $th.click(function(){
          var index = $(this).index();
          var asc = $(this).attr('data-asc');
          isAsc = asc === undefined ? true : (asc > 0 ? true : false);
          doSort(that.$table.find("tbody"), index, compFunc, isAsc);
          $(this).attr('data-asc', 1 - (isAsc ? 1 : 0));
        });
        $th.css({'cursor': 'pointer'})
           .attr('title', '点击以'+elem.innerText+'为依据排序');
      };
      need_sort.forEach(function(item){init(item)});
    }
window.Lazyload.js(window.TEXT_VARIABLES.sources.jquery, function(){sortTable();})
</script>
