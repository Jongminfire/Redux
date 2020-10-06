# Redux

1. ###  Redux 란?

   Redux는 상태 관리 라이브러리로써 컴포넌트의 상태 관련 로직들을 다른 파일로 분리시켜 효율적으로 관리 할 수 있고 컴포넌트끼리 상태를 공유할 때 여러 컴포넌트를 거치지 않고 쉽게 상태 값을 전달 할 수 있다.

   <br>

2. ### Redux의 개념

   - #####  Store (스토어)

     Redux 에서는 한 애플리케이션 당 하나의 스토어를 만들게 된다. 스토어에는 현재의 State와 Reducer가 들어가 있고 추가적인 내장 함수들이 있다.

     <br>

   - ##### Reducer (리듀서)

     리듀서는 변화를 일으키는 함수로 State에 새로운 상태를 반환한다.

     ```javascript
     function reducer(state, action){
     	// ...상태 업데이트 로직
     	return newState;
     }
     ```

     `state` 와 `action` 두 가지의 파라미터를 받으며 반환 할 새 상태를 return 해준다.

     <br>

   - ##### Action (액션)

     상태에 변화가 필요 할 때 액션을 발생시켜야 한다. 액션은 하나의 객체로써 표현되는데

     ```javascript
     {
         type:"TYPE_NAME"
     }
     ```

     형식처럼 `type` 필드를 필수적으로 포함하는 형식이다.

     ```javascript
     {
         type: "CREATE_USER",
         user: {
             name:"Lee jongmin",
             age:25
         }
     }
     ```

     처럼 type 이외의 값을 마음대로 넣을 수 있다.

     <br>

   - ##### Dispatch (디스패치)

     디스패치는 스토어 내장 함수 중 하나로써, 액션을 발생 시키는 역할을 한다.

     ```javascript
     let state = store.getState();
     let action = {type:'SELECT', id:1};
     store.dispatch(action);
     ```

     위 처럼 `dispatch`는 `action`을 파라미터로 전달해야 한다.

     <br>

     `dispatch`를 호출하게 되면 `store`는 `reducer` 함수를 실행시켜서 새로운 상태를 만들게 된다.

     <br>

   - ##### Subscribe (구독)

     구독은 스토어의 내장 함수중 하나로써 액션이 디스패치 되었을 때 마다 전달한 함수가 호출되는 함수이다.

     ```javascript
     let state = store.getState();
     
     function article = {
         //... 디스패치를 포함한 함수
     }
     
     state.subscribe(article);
     ```

     위와 같은 형태를 가지며 위에서 article 내의 액션이 디스패치가 될 경우에 article 함수를 실행시켜준다.

     <br>

     이를 활용하여 변경 내용을 UI에 적용 시켜주는 기능을 구현 할 수 있다.

