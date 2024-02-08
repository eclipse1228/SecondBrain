```jsx
class App extends Component {
constructor(props){
	super(props);
	this.state = { 
	subject:{title:'WEB', sub:'World Wid Web!'}
	}
}
render() { 
	return (
		<div className="App">
			<Subject 
				title={this.state.subject.title} sub="world wide web!">
				sub={this.state.subject.sub}>
			</Subject> 
			<TOC></TOC>
			<Content title=HTML" desc="HTML is HyperText Markup Language."></Content>
			</div>
			);
			}
}
```

1. Component를 실행할때 Constroct를 먼저 실행한다. super
	state값을 초기화하자
2.  App.js 는 index.js를 사용하고있다.  (index.js 에 App을 사용하고있다. )
	외부로부터 정보를 은닉한다. 은닉성!

```jsx
index.js file 

ReactDom.render{App / >, document.getElementById('root')}
```
2. 외부에서는 index.js를 보고 있지만, App 밖에 못 본다. !

## App이 내부적으로 사용 할 것들은 state에서 사용한다. 

[[State_key]]

![[State_key]]
