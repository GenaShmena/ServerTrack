# ServerTrack
Solution created in VS 2015, includes ServerTrack Web project and WebClientConsole to utilize it.
Web project uses MS SQL db as a repository (there is SqlScripts.sql file included. 
It creates data base ServerTrack and table PerfCounters). 
ServerTrack project uses local IIS for hosting. 
If changed that also should be changed in app.config in WebClientConsole.
Also connection string for data base need to be changed in both web.configs and app.config.
Once these are done WebClientConsole can be used to do GET and POST (assuming there is some data in db).

Examples how to do POST:
"WebClientConsole /V:p /M:5" or "WebClientConsole /V:p /S"
V stands for "Verb" (POST vs GET) 
M - multithreading POST, 
5 - specifies number of threads to create  
S - single thread 
There is a System.Timer for multithreading POST. 
It fires (by default) evey 15 sec. This can be changed in app.config in "appSetting" section key "Frequency". 

Examples how to do GET:
"WebClientConsole /v:G  /s:Computer Name /t:[1|24]"
G - "GET"
S - Computer Name to get record for
T - 1 or 24 (for last hour or last 24 hours. Last 24 hours returns average for each hour).
