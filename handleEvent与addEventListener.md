# handleEvent与addEventListener

​	`create by hqh 2018-01-09`

* ```js
  addEventListener(el,listener,false)
  其中listener接口要求实现handleEvent方法，function默认实现listener接口，对象添加handleEvent方法同样可实现接口				
  ```


* 第二个参数为function时，函数中的`this`指向目标元素对象，为object时，`this`指向此对象，可以访问对象中的私有属性

* 示例代码

  ```js
  var obj = {
  	handleEvent : function(event) {
        switch(event.type) {
          case 'touchstart':
          case 'pointerdown':
          case 'mousedown':
            this._start(event);
            break;
           case 'touchmove'：
           case 'pointermove':
           case 'mousemove':
            this._move(event);
            break;
           case 'touchend':
           case 'pointerup':
           case 'mouseup':
           	this._end(event);
           	break;
        };
        _start : function(event){}
        _move : function(event){}
        _end : functin(event){}
  	}
  	ele.addEventListener(type, obj, false)
  ```

