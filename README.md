# 123
123
@ -12,6 +12,10 @@ dependencies {
    compile('com.sparkjava:spark-core:2.9.0')
    compile('com.sparkjava:spark-template-handlebars:2.7.1')
    compile('ch.qos.logback:logback-classic:1.2.3')
    testCompile('org.junit.jupiter:junit-jupiter:5.4.2')
    testCompile('org.assertj:assertj-core:3.11.1')
}
    testCompile('org.junit.jupiter:junit-jupiter:5.6.0')
    testCompile('org.assertj:assertj-core:3.15.0')
}

test {
    useJUnitPlatform()
}
@ -26,7 +26,7 @@
     <td >작성일</td>
  </tr>
<c:choose>
  <c:when test="${articlesList ==null }" >
  <c:when test="${empty articlesList }" >
    <tr  height="10">
      <td colspan="4">
         <p align="center">
@ -35,7 +35,7 @@
      </td>  
    </tr>
  </c:when>
  <c:when test="${articlesList !=null }" >
  <c:when test="${!empty articlesList}" >
    <c:forEach  var="article" items="${articlesList }" varStatus="articleNum" >
     <tr align="center">
	<td width="5%">${articleNum.count}</td>
