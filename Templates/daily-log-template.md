---  
creation Date: <% tp.file.creation_date()%>  
tags:  
- Daily  
- timeperiods/date/<%tp.file.title%>  
- timeperiods/weekday/<%tp.date.now("dddd",0,tp.file.title,"YYYY-MM-DD")%>  
- timeperiods/week/<%tp.date.now("YYYY-[W]ww",0,tp.file.title,"YYYY-MM-DD")%>  
- timeperiods/quarter/<%tp.date.now("YYYY-[Q]Q",0,tp.file.title,"YYYY-MM-DD")%>  
- timeperiods/years/<%tp.date.now("YYYY",0,tp.file.title,"YYYY-MM-DD")%>  
linklist:  
- "[[ChangeLog]]"  
- "[[<%tp.date.now("YYYY-[W]ww",0,tp.file.title,"YYYY-MM-DD")%>]]"  
aliases:  
---  
<< [[02 Periodic Notes/01 Daily Notes/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('YYYY') %>/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('MM MMMM') %>/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('YYYY-MM-DD') %>|Yesterday]] | [[02 Periodic Notes/01 Daily Notes/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('YYYY') %>/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('MM MMMM') %>/<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').add(1, 'd').format('YYYY-MM-DD') %>|Tomorrow]] >>  
# Task Overview  
>[!todo]+ Task List  
>```tasks  
>not done  
>group by function task.happens.category.groupText  
>short mode  
>sort by tag  
>sort by priority  
>```  
# Today  
## [[ChangeLog|Change Log]]  
```dataview  
list  
WHERE file.cday = date("<%tp.file.title%>") OR file.mday = date("<%tp.file.title%>")  
WHERE file.path != this.file.path  
WHERE !contains(file.folder, "80 Gitlab Issues") AND !contains(file.folder, "02 Periodic Notes")  
sort file.name asc  
```  
## Open [GitLab]([https://gitlab.com/](https://gitlab.com/)<COMPANY>) [Issues]([https://gitlab.com/](https://gitlab.com/)<COMPANY>/<PROJECT>/<REPO>/-/issues/?sort=created_date&state=opened&assignee_username%5B%5D=<USER>&first_page_size=100) not on `Board::Done`  
```dataview  
TABLE WITHOUT ID file.link AS "Task", project AS "Project" from "80 Gitlab Issues"  
```  
## Notes and Tasks  
<%tp.file.cursor()%>  
## Meetings  
```dataview  
LIST  
WHERE contains(tags, "date/<%tp.file.title%>") AND contains(tags, "Meeting")  
```  
## Journal  
>[!success]+ Tasks Done Today  
>```tasks  
>done <% tp.date.now("YYYY-MM-DD") %>  
>short mode  
>```