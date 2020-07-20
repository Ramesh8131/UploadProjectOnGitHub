## Spring DATASOURCE (DataSourceAutoConfiguration & DataSourceProperties)
spring.datasource.driver-class-name=com.mysql.jdbc.Driver
spring.datasource.url = jdbc:mysql://localhost:3306/coachmove?createDatabaseIfNotExist=true&sessionVariables=sql_mode=''&useUnicode=yes&characterEncoding=UTF-8
spring.datasource.username = myuser
spring.datasource.password = mypass
#BN0SbVAJE3kewWU1
## Hibernate Properties
# The SQL dialect makes Hibernate generate better SQL for the chosen database
spring.jpa.properties.hibernate.dialect.storage_engine=innodb
#spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL57Dialect

# Hibernate ddl auto (create, create-drop, validate, update)
spring.jpa.hibernate.ddl-auto = update
spring.devtools.livereload.enabled=true
spring.devtools.restart.enabled=true

server.servlet.context-path=/CoachMove
server.port=8001

spring.jpa.show-sql=true
spring.h2.console.enabled=true

spring.thymeleaf.prefix=/frontend/
spring.thymeleaf.suffix=.html
spring.thymeleaf.encoding=UTF-8
spring.thymeleaf.servlet.content-type=text/html
spring.thymeleaf.mode=LEGACYHTML5
spring.thymeleaf.cache=false

spring.servlet.multipart.max-file-size =20MB 
spring.servlet.multipart.max-request-size=20MB







package com.app.coachmove.controllers;

import java.util.HashMap;
import java.util.Map;

import javax.validation.Valid;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.stereotype.Controller;
import org.springframework.validation.BindingResult;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;

import com.app.coachmove.models.ContactUs;
import com.app.coachmove.models.User;
import com.app.coachmove.services.IContactUsService;
import com.app.coachmove.services.IUserService;

@Controller
@RequestMapping("/api/")
public class ContactUsController {

	@Autowired
	IContactUsService contactUsService;
	
	@Autowired
	IUserService userService;
	
	@RequestMapping(value="users/{id}/contactUs",method=RequestMethod.POST)
	public ResponseEntity<Map<String, Object>> contactUs(@PathVariable("id") Long id,@RequestBody @Valid ContactUs contactUs,
			BindingResult result) {
		Map<String ,Object> response =new HashMap<String, Object>();
		if(contactUs == null) {
			response.put("data", "");
    		response.put("status", "Fail");
    		response.put("code", "400");
    		response.put("message", "Bad Request");
    		return new ResponseEntity<>(response, HttpStatus.BAD_REQUEST);	
		} else if(result.hasFieldErrors()) {
			response.put("data", "");
    		response.put("status", "Fail");
    		response.put("code", "400");
    		response.put("message",result.getFieldError());
    		return new ResponseEntity<>(response, HttpStatus.BAD_REQUEST);			
		} else {
			User  user = userService.findById(id);
			contactUs.setUser(user);
			contactUsService.save(contactUs);
			
			response.put("data", "");
    		response.put("status", "OK");
    		response.put("code", "200");
    		response.put("message","We have received your query and will revert you on given email address soon.");
    		return new ResponseEntity<>(response, HttpStatus.OK);
			
		}
		
	}
	
}


























# How to Upload Project On GitHub Website

This is not complex to upload project on github and how to show commit of project.

# % Follow Steps for Upload project on gitHub %

Step-1 
:- Login your's GitHub Account.
<br />
Step-2
:- Create new repository (or for more help show image pic1.png and pic2.png)
<br />
Step-3
:-Open Command Prompt
<br />
Step-4
:- Go to Current working directory where your project
<br />
(Ex--Like Project Name "Java" then run cmd "cd Java")
<br />
Step-5
:- git init
<br />
Step-6
:- git add .
<br />
Step-7
:- git commit -m "Add all my files"
<br />
Step-8
:-git remote add origin https://github.com/yourusername/your-repo-name.git   
# if not working
for more help show image pic3.png and from here copy cmd and run on your Command Prompt
<br />
Step-9

:-git push -u origin master 
# if not working
then show image  pic4.png and from here copy cmd and run on your Command Prompt
<br />
Step-10 
# Show commit of your project
:- git log 
<br />
# Ex---
 pc@linux:~/Downloads/GIT/UploadProject$ <b> git log</b>
 <br />
 commit l8ab9f78534a5g8de5d90ac15cdf796afd770e8e (HEAD -> master, origin/master)
 Author: Your Name <you@example.com>
 Date:   Thu Aug 29 10:07:30 2019 +0530

   add all my files
# this is Your Commit:--l8ab9f78534a5g8de5d90ac15cdf796afd770e8e
![alt text](https://raw.githubusercontent.com/Ramesh8131/UploadProjectOnGitHub/master/Screenshot%20from%202019-08-30%2010-17-53.png)
