# param-of-url
js获取url参数
+ 方法一 正则表达式
  ----
      function getQueryString(name) { 
          var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)", "i"); 
          var r = window.location.search.substr(1).match(reg); 
          if (r != null) return unescape(r[2]); 
          return null; 
      } 
  ----
+ 方法二
  ----
      function GetRequest() {  
         var url = location.search; //获取url中"?"符后的字串  
         var theRequest = new Object();  
         if (url.indexOf("?") != -1) {  
            var str = url.substr(1);  
            strs = str.split("&");  
            for(var i = 0; i < strs.length; i ++) {  
               theRequest[strs[i].split("=")[0]]=unescape(strs[i].split("=")[1]);  
            }  
         }  
         return theRequest;  
      }  
  ----
+ 方法三
  ----
      function getParam(paramName) { 
          paramValue = "", isFound = !1; 
          if (this.location.search.indexOf("?") == 0 && this.location.search.indexOf("=") > 1) { 
              arrSource = unescape(this.location.search).substring(1, this.location.search.length).split("&"), i = 0; 
              while (i < arrSource.length && !isFound) arrSource[i].indexOf("=") > 0 && arrSource[i].split("=")[0].toLowerCase() ==                       paramName.toLowerCase() && (paramValue = arrSource[i].split("=")[1], isFound = !0), i++ 
          } 
          return paramValue == "" && (paramValue = null), paramValue 
      } 
  ----
+ 其他参数获取介绍： 
  //设置或获取对象指定的文件名或路径。
  alert(window.location.pathname);

  //设置或获取整个 URL 为字符串。
  alert(window.location.href);

  //设置或获取与 URL 关联的端口号码。
  alert(window.location.port);
  
  //设置或获取 href 属性中在井号“#”后面的分段。
  alert(window.location.hash);

  //设置或获取 href 属性中跟在‘？’后面的部分。
  alert(window.location.search);
