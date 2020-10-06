Redux는 복잡성을 낮추어서 복잡한 어플리케이션 개발을 가능하게 한다.

하나의 객체 (state)에 데이터를 넣는 방식으로 복잡성을 해결한다.



Redux로는 디스패처, 리듀서로만 데이터를 변경 할 수 있다.



store 안에는 state 라는 정보가 있음.



var store = Redux.createStore(reducer); 형식으로 만드는데 reducer가 필요함.



reducer 은 함수로써



function reducer (oldState,action){

}

형식이다



render은 UI를 만들어주는 역할을 한다.



function render(){

​	var state = store.getState();

​	document.querySelector('#app').innerHTML = .... 

}



형식



subscribe는 state가 바뀔때마다 렌더가 되면서 UI가 갱신되는데

store.subscribe(render); 형식이다.



action은 

{type:'create', payload:{title:title, desc:desc}} 형식으로 dispatch를 통해 보낼 것이다.



dispatch는 

1. reducer을 호출해서 state 값을 바꾼다
2. subscribe을 이용해서 render를 호출해준다



dipsatch가 reducer을 호출 할 때에는 현재의 state 값과 action 값을 전달한다.



reducer은 return 값에 새로운 state 값을 준다.



객체를 복사할 때에는 

Objcect.assign() 을 이용하는데

assign을 할때에는 맨처음엔 무조건 빈 객체인 {}를 적고 그 뒤에는 속성을 적는다.



Object.assign({},{name:'leejongmin'},{city:'seoul'});

-> {name:"leejongmin,city:"seoul"}

