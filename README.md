# hello-world
my first project
var xhr = new new XMLHttpRequest();
xhr.onreadystatechange = function(){
	if(xhr.readyState==4){
		if((xhr.status>=200 && xhr.status<300) || xhr.status==304){
			alert(xhr.responseText);
		}
		else{
			alert("unsuccessful"+xhr.statusText);
		}
	}
};
xhr.open(get,"",flase);
xhr.send(null);
//--------------------------------------------
var EventUtil = {
	addHandler: function(element, type, handler){
		if(element.addEventListener){
			element.addEventListener(type,handler,false);
		}
		else if(element.attachEvent){
			element.attachEvent("on"+type,handler);
		}
		else{
			element["on"+type]=handler;
		}
	},
	removeHandler: function(element, type, handler){
		if(element.removeEventListener){
			element.removeEventListener(type,handler,false);
		}
		else if(element.dettachEvent){
			element.dettachEvent("on"+type,handler);
		}
		else{
			element["on"+type]=null;
		}
	},
	getEvent: function(event){
		return event? event:window.event;
	},
	getTarget: function(event){
		return event.target || event.srcElement;
	},
	preventDefault: function(event){
		if(event.preventDefault){
			event.preventDefault();
		}
		else{
			event.returnValue = false;
		}
	},
	stopPropagation: function(event){
		if(event.stopPropagation){
			event.stopPropagation();
		}
		else{
			event.cancelBubble = true;
		}
	}
};
//-----------------------------------------------------
function clone(obj){
	var buf;
	if(obj instanceof Array){
		buf = [];
		var i = obj.length;
		while (i--) {
			buf[i]=clone(obj[i]);
		}
		return buf;
	}
	else if(obj instanceof Object){
		buf = {};
		for(var i in obj){
			buf[i] = clone(obj[i]);
		}
		return buf;
	}
	else{
		return buf;
	}
}
//----------------------------------------------
