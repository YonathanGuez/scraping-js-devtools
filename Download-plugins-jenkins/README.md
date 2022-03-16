# Download Plugin Jenkins

Demonstration download plugins jenkins in on script  

## Site :
Go to :
```
https://updates.jenkins-ci.org/download/plugins/
```
## Open Devtool with F12:
go to Console :
past :
```

// Set each download all 1 min
let triggerDelay = 200;
let removeDelay = 60000;
let url_arr=[];

// Get all links downloaded
var lista = document.querySelectorAll('a');
for(var i =0; i< lista.length;i++){ 
	var text_url = lista[i].innerText;
	text_url =text_url.replace('/','')
	var link_url = 'https://updates.jenkins-ci.org/latest/'+text_url +'.hpi'
	url_arr.push(link_url)
}	

// Run the function download for each links 
url_arr.forEach(function(item,index){
    _createIFrameDownload(item, index * triggerDelay, removeDelay);
})

function _createIFrameDownload(url, triggerDelay, removeDelay) {
    //Add iframe dynamically, set SRC, and delete
    setTimeout(function() {
	var frame = document.createElement('iframe');
        frame.setAttribute('class', 'multi-download'); // assign an class
        frame.setAttribute('style', 'display: none;');
        frame.setAttribute('src', url);
        document.body.appendChild(frame);
        setTimeout(function() {
            frame.remove();
        }, removeDelay);
    }, triggerDelay);
}

```