### ＧＡＬＡＸＹＣＥＮＴＵＲＹ

You can use the [editor on GitHub](https://github.com/galaxycentury/galaxycentury.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

<a href="https://www.baidu.com/"><img src="galaxycentury.github.io/baidu.png" style="float:middle" width="50%" height="50%" border="nor">

### 星河世纪/银河世纪

Welcome to this website<br>
http://2003.ink<br>
http://galaxycentury.com<br>
http://galaxycentury.net<br>
[HTTP](http://galaxycentury.com/)/[HTTPS](https://galaxycentury.com/)
如有疑问,请联系我们 [email](galaxycentury@outlook.com) galaxycentury@outlook.com

<!---
### 常用软件类

[Windows Kmplayer 影音全能播放器安装包X86](https://vdo.kmplayer.com/down/kmp32/KMPlayer_4.2.2.53.exe)<br>
[Windows Kmplayer 影音全能播放器安装包X64](https://vdo.kmplayer.com/down/kmp64x/KMP64_2021.06.24.14.exe)<br>

<br>
[Windows Firefox Browser 火狐浏览器 官方安装包](https://download-ssl.firefox.com.cn/releases-sha2/stub/official/zh-CN/Firefox-latest.exe)<br>

[Windows 7 64 位版本和 Windows Server 2008 R2 64 位版本 Internet Explorer 11](https://download.microsoft.com/download/5/6/F/56FD6253-CB53-4E38-94C6-74367DA2AB34/IE11-Windows6.1-x64-zh-cn.exe)<br>[Windows 7 32 位版本 Internet Explorer 11](https://download.microsoft.com/download/F/2/8/F2871AC4-E82B-4636-BB37-A5F2B14C8616/IE11-Windows6.1-x86-zh-cn.exe)<br>[Windows Flash Player]( https://www.flash.cn/cdm/latest/flashplayerpp_install_cn.exe)

### 防病毒软件类

[安装包](https://)

### 网络工具类

### ＧＡＬＡＸＹＣＥＮＴＵＲＹ
-->
<!---
<IMG src="galaxycentury.github.io/E709F37A-6896-4535-9756-45C5F58767C3.jpeg" height=620 width=416><IMG src="galaxycentury.github.io/47BEEF4B-5DEE-4602-A6C2-315E15B365A2.jpeg" height=620 width=416>
<center></center>
-->

### Markdown

ＧＡＬＡＸＹＣＥＮＴＵＲＹ
 
 致力于提供高质量的软件下载平台,如需投稿请您通过EMAIL将软件或代码链接地址发送给我们！

 
 
 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    #snailPlayId {
      width: 800px;
      height: 500px;
      margin: 0 auto;
    }
    h1 {
      text-align: center;
    }
  </style>
</head>
<body>
<h1>snail-player</h1>
<div id='snailPlayId'></div>

</body>
<script type="module">
  import SnailPlayer from "./lib/index.js";
  new SnailPlayer({
    el: '#snailPlayId',
    src: 'https://webrabbit.oss-cn-beijing.aliyuncs.com/drawingbed/video.mp4',
    autoplay: true, // 是否自动播放
    loop: true // 是否循环播放
  })
</script>
</html>

 // 计算进度条时间
progressTime(offsetY) {
  return utils.formatSeconds((offsetY / this.progressw * this.playVideo.duration).toFixed(2))
}


// 进度条计算公式
progressCalculate() {
  return (this.progressw / this.playVideo.duration * this.playVideo.currentTime).toFixed(2)
}


// 全屏
fullScreenFun() {
  const docElm = document.documentElement
  if (!this.isFullScreen) {
    utils.addClass(this.el, 'fullscreen-active')
    utils.addClass(this.playVideo, 'fullscreen-active')
    utils.showClass('snail-player-full-screen-icon')
    utils.hiddenClass('snail-player-fullscreen-btn')
    utils.changeInnerText('fullscreen-icon', '退出全屏')
    utils.addClass(this.playBottom, 'sn-player-fullscreen-bottom-active')
    setTimeout(() => {
      if (docElm.requestFullscreen) {
        docElm.requestFullscreen();
      } else if (docElm.mozRequestFullScreen) {
        docElm.mozRequestFullScreen();
      } else if (document.webkitRequestFullScreen) {
        docElm.webkitRequestFullScreen();
      }
    }, 100)
    this.isFullScreen = true
    utils.hiddenClass('snail-player-web-fullscreen-box')
  } else {
    if (document.exitFullscreen) {
      document.exitFullscreen();
    } else if (document.mozCancelFullScreen) {
      document.mozCancelFullScreen();
    } else if (document.webkitCancelFullScreen) {
      document.webkitCancelFullScreen();
    }
    utils.showClass('snail-player-web-fullscreen-box')
    utils.removeClass(this.el, 'fullscreen-active')
    utils.removeClass(this.playVideo, 'fullscreen-active')
    utils.hiddenClass('snail-player-full-screen-icon')
    utils.showClass('snail-player-fullscreen-btn')
    utils.changeInnerText('fullscreen-icon', '进入全屏')
    utils.removeClass(this.playBottom, 'sn-player-fullscreen-bottom-active')
    this.isFullScreen = false
  }
}

 //加载css
renderCss(url) {
  var head = document.getElementsByTagName('head')[0];
  var link = document.createElement('link');
  link.type='text/css';
  link.rel = 'stylesheet';
  link.href = url;
  head.appendChild(link);
}

//加载favicon
renderIcon(url) {
  var head = document.getElementsByTagName('head')[0];
  var link = document.createElement('link');
  link.type='type="image/x-icon"';
  link.rel = 'shortcut icon';
  link.href = url;
  head.appendChild(link);
}
 
 
class Utils {
  hasClass(ele, cls) {
    return !!ele.className.match(new RegExp('(\s|^)' + cls + '(\s|$)'))
  }
  addClass(ele, cls) {
    if (!this.hasClass(ele, cls)) ele.className += ' ' + cls
  }
  removeClass(ele, cls) {
    if (this.hasClass(ele, cls)) {
      const reg = new RegExp('(\s|^)' + cls + '(\s|$)')
      ele.className = ele.className.replace(reg, '')
    }
  }
  set(key, value) {
    localStorage.setItem(key, value)
  }

  get(key) {
    return  localStorage.getItem(key)
  }
  showClass(cls) {
    cls ? document.getElementsByClassName(cls)[0].style.display = 'block' : new Error('请输入类名')
  }
  hiddenClass(cls) {
    cls ? document.getElementsByClassName(cls)[0].style.display = 'none' : new Error('请输入类名')
  }
  changeInnerText(cls, text) {
    document.getElementsByClassName(cls)[0].innerHTML = text
  }

  clickfu(to, cls){
    //回调函数，to为点击对象
    to.setAttribute("class",cls);
    const siblings = to.parentNode.childNodes;
    for(let i=0; i<siblings.length; i++)
      if(siblings[i].nodeType == 1 && siblings[i] != to)siblings[i].className = '';
  }

  formatSeconds(value) {
    if(!value) return '00:00'
    value = parseInt(value);
    let time;
    if (value > -1) {
     let hour = Math.floor(value / 3600);
     let min = Math.floor(value / 60) % 60;
     let sec = value % 60;
     let day = parseInt(hour / 24);
      if (day > 0) {
        hour = hour - 24 * day;
        time = day + "day " + hour + ":";
      } else if (hour > 0) {
        time = hour + ":";
      }else {
        time = "";
      }
      if (min < 10) {
        time += "0";
      }
      time += min + ":";
      if (sec < 10) {
        time += "0";
      }
      time += sec;
    }
    return time;
  }

  classEle(cls) {
    return  cls && document.getElementsByClassName(cls)[0]
  }

}

export default Utils
 
 
 
ＧＡＬＡＸＹＣＥＮＴＵＲＹ

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).



<IMG src="galaxycentury.github.io/20220729001.jpg" height=320 width=824>
 
<!---
### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/galaxycentury/galaxycentury.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
-->
 
###galaxycentury@Outlook.com
