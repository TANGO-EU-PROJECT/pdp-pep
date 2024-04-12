GUIDE TO EXECUTE PEP/PDP SERVER:

1. Firstly, you have the demo folder. You will need to execute ./gradlew build

2. When you get the BUILD SUCCESSFUL, build the Docker image with this command: docker-compose build

3. The file .env contains the environment variables where you can set the port where the service will be listening, the policies or trust scores configuration...

4. Then, with the configuration set you will run the docker container: docker-compose up -d

5. The server will be running on 8088. Send the next request to http://localhost:8088/api/connector-access-token (from POSTMAN, curl...).

	{
    "didSP": "tangoUser",
    "sar": {
        "action": "GET",
        "resource": "/temperatura"
    },
    "didRequester": "did",
    "accessToken":"eyJhbGciOiJFUzI1NiIsImtpZCI6Ik9XOFdKcDJRREtyRldUNVpPZ2IzWWd2eXRNVGR6RWFMNU93bm5MWkVTVUEiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOlsiMTAuNjQuNDUuNTg6NTAwMCJdLCJjbGllbnRfaWQiOiJkaWQ6d2ViOmlwcy5kc2JhLmF3cy5uaXRsYWIuaW86ZGlkIiwiZXhwIjoxNzA3ODM2MDU1LCJpc3MiOiJkaWQ6d2ViOmlwcy5kc2JhLmF3cy5uaXRsYWIuaW86ZGlkIiwia2lkIjoiT1c4V0pwMlFES3JGV1Q1Wk9nYjNZZ3Z5dE1UZHpFYUw1T3dubkxaRVNVQSIsInN1YiI6ImRpZDpteTp3YWxsZXQiLCJ2ZXJpZmlhYmxlQ3JlZGVudGlhbCI6eyJAY29udGV4dCI6WyJodHRwczovL3d3dy53My5vcmcvMjAxOC9jcmVkZW50aWFscy92MSIsImh0dHBzOi8vdzNpZC5vcmcvc2VjdXJpdHkvc3VpdGVzL2p3cy0yMDIwL3YxIl0sImNyZWRlbnRpYWxTY2hlbWEiOnsiaWQiOiJodHRwczovL3Jhdy5naXRodWJ1c2VyY29udGVudC5jb20vRklXQVJFLU9wcy90ZWNoLXgtY2hhbGxlbmdlL21haW4vc2NoZW1hLmpzb24iLCJ0eXBlIjoiRnVsbEpzb25TY2hlbWFWYWxpZGF0b3IyMDIxIn0sImNyZWRlbnRpYWxTdWJqZWN0Ijp7ImVtYWlsIjoic3RhbmRhcmQtZW1wbG95ZWVAaXBzLm9yZyIsImlkIjoiODJmZDA0MDUtNGFmMC00ZjM5LWEyNzQtOGU4MjM3NGY0N2I1IiwibGFzdE5hbWUiOiJJUFMiLCJyb2xlcyI6W3sibmFtZXMiOlsiR09MRF9DVVNUT01FUiJdLCJ0YXJnZXQiOiJkaWQ6d2ViOmlwcy5kc2JhLmF3cy5uaXRsYWIuaW86ZGlkIn1dLCJ0eXBlIjoiZ3g6TmF0dXJhbFBhcnRpY2lwYW50In0sImlkIjoidXJuOnV1aWQ6OTVmN2QwYTgtYjliNi00ZWIwLTgwNjYtZDUwYjk2ZTc4NjkzIiwiaXNzdWFuY2VEYXRlIjoiMjAyNC0wMi0xM1QxNDowNjo1MloiLCJpc3N1ZWQiOiIyMDI0LTAyLTEzVDE0OjA2OjUyWiIsImlzc3VlciI6ImRpZDp3ZWI6aXBzLmRzYmEuYXdzLm5pdGxhYi5pbzpkaWQiLCJwcm9vZiI6eyJjcmVhdGVkIjoiMjAyNC0wMi0xM1QxNDowNjo1MloiLCJqd3MiOiJleUppTmpRaU9tWmhiSE5sTENKamNtbDBJanBiSW1JMk5DSmRMQ0poYkdjaU9pSlFVekkxTmlKOS4ubnpBdzlZM00wMHVDRG1uemtEVUtfMkdDSU5GNEFPYmJmakMwWWVCSE4wTmhOaERDX2xZMHZPYVVGbkNEaGZCakg3OE1rWmNvaDhjYWYtYXEzcWRYaXRDS2VDbm9OQS1rdXI0azNYNmV0M1JWQkJSQUp2LXJWRXZHVmprcExjVV9YdXN2ZjhOZzVLOU8xRElESHNJOFR2ZDJ1WFRuWEc3ZUpILTgzZnRDZ0VfYzZ1blFQLTNuR1hBdkliSmQxeENQbTgxUlU0clkzRC1VMi0tQzlYbzhLaTJ6bHNNSVFHNVJlSm5XNG02dmNFQzh6a21nQkdURlE3MkhqTWZQdUs3QjV1SndIdXhXTUpWRVZOQ3hPZDdxTFZYMEF2N1NpZDZDZ1VpdTFNWjl6YlN5UnVFdDdrdDFYZVRNRmlkMEx4NDIyMnhydWxnY1VQbHMwSEhjcjJMQTk4cV9lem1fY2ZLWmRUT2pFRWJhZzdWX1BlMjVsbjVSRzBaZnNEYk01WVBFSnlzNDBpMGcyd0lBWEVVVW5CY1pRMmh5SnhPalhaMVBtNGtlcW0ydEFNQXZtUnA3amkzVDhJelJNQU9NT2RRSFJtTE1ENW5idDhfY2lOYlJrVUtDbnBxcjlRQXhSa0NEa0s5Z3B0RzNIV3AydkVwNzVzZWhjbV9DVE9NZ1RTRzJ6UkNBb3E5YmRtNDN4bmpBalNyck5tWHJmRkVuQmxGY3R4TTloekRNMUxMNHBHc1Z1TVJIWFJvUlZIOE9Rbm4zQnVMVWRmNUVQeFFsZTdfanB0ekgxSnBsWDFRMmlfQnBvQVVSWDFKZnVMazViVF9hbktLTmctUXprMGoyNlNETU5uTTl0Qm80ZXVZckVIQV9WVXJYbmVxSm5hMTdVanN2R0lUMzFXaUtWZmsiLCJ0eXBlIjoiSnNvbldlYlNpZ25hdHVyZTIwMjAiLCJ2ZXJpZmljYXRpb25NZXRob2QiOiJkaWQ6d2ViOmlwcy5kc2JhLmF3cy5uaXRsYWIuaW86ZGlkIzM4OWUxOTNlYzI5ZTQ0ODVhMjljOWYyYTMzY2Q0NDYwIn0sInR5cGUiOlsiRW1wbG95ZWVDcmVkZW50aWFsIl0sInZhbGlkRnJvbSI6IjIwMjQtMDItMTNUMTQ6MDY6NTJaIn19.eKqz-eduU-SDkvuPYFu6UvVM7Ga5Xa6VsNDk4L_S113ugIBLEb_QXbxyWlxdP4XXSuBbQTiDz0FAx15wgmFXvQ"
}

6. This request will be returning a JSON Object called "ct". This is the capability token that allows the requester to access the resource and make an action.
		{"id":"9ba04d2e","ii":"1707469280053","is":"erat","su":"did","de":"natalia","si":"Rpx4qckhPrCWAXTK6rgYruYG6srzx7fIdfVmUrB5T7xYy84HMZMLX8PbIVb7nDdNeTLJXXD38y54WObl973fGQmmYwD7cvPnLikaVyyNvvXrg9a8FjvqxEoHflKGPtkY8tjXvSs65LRMkOuckWMejqMhG1R95wyUdmhGhh4grjbTIYtpQZTBFT57S1DHgUJrrkcJcLJDKbF30pZnOuxrxBraezil67DHchfXehFT2/IpsQadZQ6TwK7k+3DyPhcPPBPSQ1yGkbV/Bm9KFVs/Eg5fI4FZrGhWU84TiVlw9JoguYg0zTuW+ZUASeTBLMFbMLB/4McCyFn0RU/JMos7iw\u003d\u003d","ar":[{"action":"GET","resource":"/temperatura"}],"nb":1707469280053,"na":1707472880053}
	
7. Send another request to http://localhost:8080/api/access-with-token with a JSON body like this, changing the "ct" for the one that returned the last request and the "sar" for the access that the token allows you to do. 
	{
    		"ct":{"id":"9ba04d2e","ii":"1707469280053","is":"erat","su":"did","de":"natalia","si":"Rpx4qckhPrCWAXTK6rgYruYG6srzx7fIdfVmUrB5T7xYy84HMZMLX8PbIVb7nDdNeTLJXXD38y54WObl973fGQmmYwD7cvPnLikaVyyNvvXrg9a8FjvqxEoHflKGPtkY8tjXvSs65LRMkOuckWMejqMhG1R95wyUdmhGhh4grjbTIYtpQZTBFT57S1DHgUJrrkcJcLJDKbF30pZnOuxrxBraezil67DHchfXehFT2/IpsQadZQ6TwK7k+3DyPhcPPBPSQ1yGkbV/Bm9KFVs/Eg5fI4FZrGhWU84TiVlw9JoguYg0zTuW+ZUASeTBLMFbMLB/4McCyFn0RU/JMos7iw\u003d\u003d","ar":[{"action":"GET","resource":"/temperatura"}],"nb":1707469280053,"na":1707472880053},
     "sar":{
        "action":"GET", 
        "resource":"/temperatura"
    }
}

8. If everything is OK, you will be getting a success message. If there's any error, you get an error message as well.
