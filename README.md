<%@ page language="java" import="java.util.*,com.vofosion.domain.*" pageEncoding="UTF-8"%>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
<%
String path = request.getContextPath();
String basePath = request.getScheme()+"://"+request.getServerName()+":"+request.getServerPort()+path+"/";
%>

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>主页</title>
<link rel="icon" href="/images/017.jpg" type="image/x-icon"/><!--title图标 -->
	<script src="js/jquery-1.8.3.min.js"></script>
	<script src="js/highcharts.js"></script>
	<script src="js/exporting.js"></script>
	<script src="js/highcharts-zh_CN.js"></script>
<style>

		  a{ color:#09F}
          a:hover{ color:#09C}/* 鼠标经过悬停字体颜色 */
          /* css 注释说明：以上代码为设置html中超链接统一字体颜色 */
          a{text-decoration:none}
		  #div a{
			  color:#FFF;
		  }
		  #div a:hover{
			  color:#3CF;
		  }
		
		 <!-- #biaoTi img{--> 
			<!--  width:170px;--> 
			<!--  height:80px;--> 
		 <!-- }--> 
		   #caiDan img{
			   width:80px;
			   height:80px;
			   
		   }
		  #c1 a{
			  color:#9DD14A;
		  }
		  #c1 a:hover{
			  color:#0C6;
		  }
		  #c2 a{
			  color:#FDA3A2;
		  }
		  #c2 a:hover{
			  color:#F99;
		  }
		  #c3 a{
			  color:#F7A16B;
		  }
		  #c3 a:hover{
			  color:#F90;
		  }
		  #c4 a{
			  color:#66D2FF;
		  }
		  #c4 a:hover{
			  color:#69F;
		  }
		  #info a{
			  color:#0033CC;
		  }
		  #info a:hover{
			  color:#03F;
		  }
		  
				  
</style>

<script type="text/javascript">

	function Layer_HideOrShow(imgObj)  

	{ 
		var divObj=document.getElementById("caiDan");  

   		if(divObj.style.display=="block")  

     	{  
			divObj.style.display="none";  

     	} else {
			divObj.style.display="block";
		} 
	
}  

</script>

</head>

<body >

<table width="100%"  height="100%" border="0" bgcolor="E9ECF1" cellspacing="15px">
  <tr >
    <td colspan="2">
    <!--标题栏 -->
    	<div style="width:100%; height:90px; background-color:#026BE0;float:left; z-index:-1">
        
			<div   id="biaoTi1" style="width:600px; height:90px; background-color:#026BE0;float:left; z-index:0">
            	<table width="100%" height="90px" border="0"  cellspacing="0" cellpadding="0">
                  <tr>
                    <td>
                    	<img style="width=150px; height:70px" src="images/15.jpg" width="122" height="66" onclick="Layer_HideOrShow(this)"/>
                    </td>
                    <td>
                    	<img  style="width=200px; height:80px" src="images/03.jpg"/>
                    </td>
                    <td >
                    	
         <!--更改 2 --> 	<div style="width=150px; height:70px; position:absolute; left:500px; top:60px">
                        	
                        	<table>
                            	<tr>
                                	<td>
                                        <font color="#0033FF">
                                            <b>我的中心</b>
                                        </font>
                                    </td>
                                    <td>
                                    <!-- 
                                    	<img  src="../images/014.jpg" style=" width:15px;height:15px"/>
                                    -->
                                    </td>
                                </tr>
                              </table>
                            
                         </div>
                   <!--更改3 -->     <img  src="images/17.jpg" style=" width=150px; height:50px"/>
                    	
                    </td>
                    
                  </tr>
                </table>
            </div>
            <%
            	List<ExtraworkInfo> e=(ArrayList<ExtraworkInfo>)request.getAttribute("extraworkInfolist");	
				int size=e.size();
				int myPoints=size*4;
             %>
          
            <div id="biaoTi2" style="width:600px; height:90px; background-color:#026BE0;float:right; z-index:0">
            	<table width="250px" height="90px" border="0"  cellspacing="0" cellpadding="0" align="right">
                  <tr>
                    <td>
                   		<font color="#FFF">欢迎您，</font><font color="#B3EEA5">${requestScope.staffInfolist.name}</font>
                    </td>
                    <td>
                    	<img style="width=30px; height:30px"src="images/13.jpg" />
                    </td>
                    <td >
                   		 <a href="quit"><img style="width=30px; height:30px"src="images/14.jpg"/></a>
                    </td>
                  </tr>
                </table>            
            </div>
        </div>
    </td>
  </tr>
  <tr>
  	<td colspan="2">
    	<div id="caiDan" style=" display:none; width:100%; height:150px; background-color:#FFF;float:left;z-index:-1">  
        	<table width="700px" height="100%" border="0" align="left">
              <tr>
                <td id="c1" align="center" style="border-right:dotted #CCC">
                	<img  src="images/06.jpg"/>
                    <br />
                    <a href="#" ><b>在线登录</b> </a>
                </td>
                <td id="c2" align="center" style="border-right:dotted #CCC">
                	<img  src="images/07.jpg"/>
                    <br />
                    <a href="#" ><b>工时查询</b> </a>                    
                </td>
                <td id="c3" align="center"style="border-right:dotted #CCC">
                	<img  src="images/08.jpg"/>
                    <br />
                    <a href="#" ><b>统计报表</b> </a>                    
                </td>
                <td id="c4" align="center"style="border-right:dotted #CCC">
                	<img  src="images/09.jpg"/>
                     <br />
                    <a href="SelectTeam" ><b>团队信息</b> </a>                   
                </td>
                <td></td>
              </tr>
            </table>
        
        </div>
    </td>
  </tr>
  <tr >
    <td id="info" width="55%" height="60%">
    	<div style="width:100%; height:500px; background-color:#FFF;float:left;z-index:-1">
          <table width="100%" height="100%" border="0">
              <tr>
                <td width="11" height="35" align="right">
                	<img  src="images/11.jpg" width="7px" height="25px"/>
                </td>
                <td width="322"align="left">
                	<b><font face="黑体"  size="+1">员工信息</font></b>
                 </td>
                <td width="234" align="right">
                	<img  src="images/12.jpg" width="25px" height="25px"/>
                </td>
                <td width="96" align="left">
                <form action="index" name="myform" method="post" >
                	<input type="hidden" name="name" value=${requestScope.staffInfolist.name} >
                	<input type="hidden" name="password" value=${requestScope.staffInfolist.password} >
                	<h4><font color="#0033CC"><a href="javascript:document.myform.submit();"> 更新</a></font></h4>
                </form>
                </td>
              </tr>
              <tr>
                <td colspan="4">
                    <table width="100%" height="100%" border="0">
                      <tr>
                        <td style=" border-top: thin dashed  #999;border-left: thin dashed #999;border-right: thin dashed #999;">
                            <table width="100%" height="100%" border="0">
                              <tr>
                                <td width="50%">
                                	<font  color="#666666"><b>姓 &nbsp;&nbsp;&nbsp;名：</b></font>
                                    <font  size="+2"color="#FF3300"><b>${requestScope.staffInfolist.name}</b></font>
                                 </td>
                                <td width="50%">
                                	<font  color="#666666"><b>工 &nbsp;&nbsp;&nbsp;号：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.userNo}</b></font>
                                </td>
                              </tr>
                              <tr>
                                <td colspan="2">
                                	<font  color="#666666"><b>入司时间：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.entry}</b></font>
                                </td>
                                </tr>
                              <tr>
                                <td colspan="2">
           <%      
           List<GroupInfo> g=(ArrayList<GroupInfo>)request.getAttribute("groupInfolist");
		   List<ExtraworkInfo> first1=(ArrayList<ExtraworkInfo>)request.getAttribute("firstOne");
           List<ExtraworkInfo> first2=(ArrayList<ExtraworkInfo>)request.getAttribute("firstTwo");
           List<ExtraworkInfo> first3=(ArrayList<ExtraworkInfo>)request.getAttribute("firstThree");	
           List<ExtraworkInfo> second1=(ArrayList<ExtraworkInfo>)request.getAttribute("secondOne");
           List<ExtraworkInfo> second2=(ArrayList<ExtraworkInfo>)request.getAttribute("secondTwo");
           List<ExtraworkInfo> second3=(ArrayList<ExtraworkInfo>)request.getAttribute("secondThree");
           int data1=first1.size()*138;
           int data2=first2.size()*92;
           int data3=first3.size()*39;
           int data4=second1.size()*81;
           int data5=second2.size()*100;
           int data6=second3.size()*93;
				int size2=g.size();                	
				
			%>
			
                                
                                	<font  color="#666666"><b>归属团队：</b></font>
                                    <font  size="+1" face="黑体">
                                    <b>福建试点项目
                                    <% for(int i=0;i<size2;i++) { 
										GroupInfo gro = g.get(i);		
									%>
                                   		<%  if(i==size2-1){%>
                                  			 <%=gro.getGroupName() %>
                                  	 	<%}else{ %>
                                  			 <%=gro.getGroupName() %>、
										<%} 
									}%>
									</b></font>
                                </td>
                                </tr>
                              
                            </table>
                        </td>
                      </tr>
                      <tr>
                        <td style=" background-color:#F8F8F8;border-left:thin dashed #999;border-right:thin dashed #999;">
                            <table width="100%" height="100%" border="0">
                              <tr>
                                <td>
                                	<font  color="#666666"><b>联系电话：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.tel}</b></font>
                                </td>
                                <td>
                                	<font  color="#666666"><b>邮箱：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.email}</b></font>
                                </td>
                              </tr>
                              <tr>
                                <td>
                                	<font  color="#666666"><b>RTX帐号：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.rtx}</b></font>
                                </td>
                                <td>
                                	<font  color="#666666"><b>通知方式：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.inforType}</b></font>
                                </td>
                              </tr>
                              <tr>
                                <td colspan="2">
                                	<font  color="#666666"><b>备注信息：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.remark}</b></font>
                                </td>
                                </tr>
                            </table>
                        </td>
                      </tr>
                      <tr>
                        <td style=" border-left:thin dashed #999; border-bottom:thin dashed #999;border-right:thin dashed #999;" >
                            <table width="100%" height="100%" border="0">
                              <tr>
                                <td>
                                	<font  color="#666666"><b>我的岗位：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.job}</b></font>
                                </td>
                                <td>
                                	<font  color="#666666"><b>我的功劳：</b></font>
                                    <font  size="+1" face="黑体"><b><%=size %>次</b></font>
                                     <font  color="#666666"><b>[<fmt:formatDate value="${requestScope.extraworkInfoshou.date}" pattern="yyyy/MM/dd"/>]至[<fmt:formatDate value="${requestScope.extraworkInfomo.date}" pattern="yyyy/MM/dd"/>]</b></font>
                                </td>
                              </tr>
                              <tr>
                                <td>
                                	<font  color="#666666"><b>我的积分：</b></font>
                                    <font  size="+1" face="黑体"><b>${requestScope.staffInfolist.myPoints}</b></font>
                                </td>
                                <td >
                                	<font  color="#666666"><b>我的苦劳：</b></font>
                                    <font  size="+1" face="黑体"><b><%=myPoints %>小时</b></font>
                                     <font  color="#666666"><b>[<fmt:formatDate value="${requestScope.extraworkInfoshou.date}" pattern="yyyy/MM/dd"/>]至[<fmt:formatDate value="${requestScope.extraworkInfomo.date}" pattern="yyyy/MM/dd"/>]</b></font>
                                </td>
                              </tr>
                            </table>
                        </td>
                      </tr>
                    </table>
                </td>
              </tr>
            </table>
        </div>
    </td>

    <td id="info" width="45%">
    	<div style="width:100%; height:500px; background-color:#FFF;float:left;z-index:-1">
          	<table width="100%" height="100%" border="0">
              <tr>
                <td width="3%" align="right">
                	<img  src="images/11.jpg" width="7px" height="25px"/>
                </td>
                <td width="55%" align="left">
                	<b><font face="黑体"  size="+1">统计信息</font></b>
                </td>
                <td width="19%" align="right">
                	<img  src="images/16.jpg" width="25px" height="25px"/>
                </td>
                <td width="23%"  align="left">
                	<h4><font color="#0033CC"> <a href="myCenter">查看</a></font></h4>
                </td>
              </tr>
              <tr>
                <td colspan="4"><div id="container" style="min-width:400px;height:400px"></div></td>
              </tr>
              <tr>
                <td colspan="4" align="center"><h3>我的近三个月加班工时统计</h3></td>
              </tr>
            </table>
        </div>
    </td>
  </tr>
  <tr>
    <td height="10%" colspan="2">
    	<div style="width:100%; height:80px; background-color:#FFF;float:left; z-index:-1">
        	<table width="100%" border="0">
  				<tr>
   					 <td>&nbsp;</td>
   					 <td align="center"><font size="-1" color="#999999">版权所有  &copy;福建富士通信息软件有限公司 </font></td>
                     <td>&nbsp;</td>
                  </tr>
                </table>

        </div>	
    </td>
 
  </tr>
</table>

<script>
	$(function () {
    $('#container').highcharts({
        chart: {
            type: 'column'
        },
        credits:{
     		enabled: false // 禁用版权信息
		},
        title: {
            text: ''
        },
        subtitle: {
            text: ''
        },
        xAxis: {
            categories: [
                '1月',
                '2月',
                '3月',
             
            ],
            crosshair: true,
			title: {
                text: '时间'
            }
        },
        yAxis: {
            min: 0,
            title: {
                text: '工时[h]'
            }
        },
        tooltip: {
            headerFormat: '<span style="font-size:12px">{point.key}</span><table width="170px" height="100%">',
            pointFormat: '<tr><td style="font-size:12px;color:{series.color};padding:0">{series.name}: </td>' +
            '<td style="padding:0;font-size:12px;"><b>{point.y:.1f}小时 </b></td></tr>',
            footerFormat: '</table>',
            shared: true,
            useHTML: true
        },
        plotOptions: {
            column: {
                pointPadding: 0.2,
                borderWidth: 0
            }
        },
        series: [
        <% 
			String gro1 = g.get(0).getGroupName();	
			String gro2 = g.get(1).getGroupName();	
		%>
        {
            name: '<%=gro1 %>',
            data: [<%=data1 %>, <%=data2 %>, <%=data3 %>]
        }, {
            name: '<%=gro2 %>',
            data: [<%=data4 %>, <%=data5 %>, <%=data6 %>]
        }]
    });
});
</script>
            
</body>
</html>
