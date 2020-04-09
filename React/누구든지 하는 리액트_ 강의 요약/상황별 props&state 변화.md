
# 전화번호부 프로젝트

## 상황별 props & state 값 변화 (객체 생성, 수정 , 삭제 시)

### 사용자가 이름, 전화번호 input 에 값을 입력하고 등록 버튼을 눌렀을 경우

props 
- App 컴포넌트에서 handleCreate 함수를 PhoneForm으로 전달

state 
- input에 값을 입력할때마다 handleChange를 실행하여 state 값을 현재 이벤트가 실행되는 input의 value 값으로 바꿈.
- 등록 버튼을 누르면 handleSubmit을 실행하여, props로 받아온 onCreate에 현재 state를 보내 information 배열에 입력 받은 값을 추가하고 id 값 1 증가시킴

### 삭제 버튼을 누른 경우

props
- App 컴포넌트에서 PhoneInfoList로 handleRemove 함수와 information 배열 전달
- props로 받은 onRemove와 information 배열의 데이터 하나씩 PhoneInfo로 전달

state
- 삭제 버튼을 누르면 handleRemove 실행하고 information 배열 중 props로 받은 현재 데이터의 id를 onRemove의 인자로 보내 information 배열에서 해당하는 id를 제외한 데이터만 남기도록 state를 바꿈.


### 수정 버튼을 누른 뒤, 수정한 내용을 입력하고 적용을 누른 경우

props
- App 컴포넌트에서 PhoneInfoList로 handleUpdate 함수와 information 배열 전달
- props로 받은 onUpdate와 information 배열의 데이터 하나씩 PhoneInfo로 전달

state
- 수정 버튼을 눌렀으므로 현재 editing 값은 true. handleToggleEdit을 호출하여 props로 받은 onUpdate에 현재 데이터의 id값과 수정된 값인 state의 name,phone 값을 인자로 보내서 information 배열의 해당 id값의 데이터를 수정하고, 현재 state의 editing 값을 false로 바꿈
