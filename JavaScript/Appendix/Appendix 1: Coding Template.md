# Appendix 1: Coding Template
```
var myCustomDiv = document.createElement('div');

function respondToTheClick(evt) {
    if (evt.target.nodeName === 'P'){
        console.log('A paragraph was clicked: ' + evt.target.textContent);
    }
    
}

for (var i = 1; i <= 200; i++) {
    var newElement = document.createElement('p');
    newElement.textContent = 'This is paragraph number ' + i;

    myCustomDiv.appendChild(newElement);
}

document.body.appendChild(myCustomDiv);

myCustomDiv.addEventListener('click', respondToTheClick);
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0MTkzOTc1NV19
-->