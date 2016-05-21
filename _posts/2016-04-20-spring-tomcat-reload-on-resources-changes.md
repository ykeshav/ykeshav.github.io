---
layout: post
title: Spring tomcat reload page whenever files changes on classpath
subtitle: Tomcat Auto reload Page on files changes
sitemap:
    priority: 1.00
    changefreq: 'daily'

---

Spring Tomcat Application auto reload Can be done in two days without using JRebel<br/>
1. Tomcat Configuration
2. By Adding Spring Boot DevTools Dependency

### Tomcat Configuration
1. Open your Tomcat Run/Debug Configuration

2. In Tomcat Server Configuration Go To **'Deployment Tab'** (2nd Tab) and add Artifact by clicking on **+** icon and select **'somewarname.war exploded'** version

3. Now Go To **'Server'** Tab(1st tab) in the same Tomcat Configuration Popup and change the **'on Update Action'** to Update Resources, **'On frame Deactivation'** setting to either 'Update resources' or 'Update Classes and Resources'
    - *Update resources:* All changed resources (that is, all application components other than the classes) will be updated.
    
    - *Update classes:* and resources. All changed resources will be updated; changed classes will be recompiled. Note that whether the actual classes will be updated depends on the capabilities web server. If I recall, Tomcat will reload html/xhtml and jsp files, but not Servlets or classes that JSPs or Servlets use. You need to modified Tomcat to use a dynamic classloader for that

4. Click Apply and OK

### Spring Boot DevTools Dependency
The `spring-boot-devtools` module provides inbuilt server auto restart/refresh whenever files on the classpath change. Add below steps in **build.gradle**<br/>

1. Add Spring boot devtools gradle dependency<br/>

   `dependencies {
        compile("org.springframework.boot:spring-boot-devtools")
    }`
    
2. For Automatic Restart/Refresh on file changes<br/>
  `bootRun {
     addResources = true
   }`
 
3. Once above steps done, restart server once if possible remove old war file and then build fresh war