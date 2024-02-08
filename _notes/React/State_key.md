## Data를 바꾼다고 로직을 바꿀 필요가 없다.
## 이때 Key라는 props가 필요하다 
- key라는 props는 우리가 필요한것이 아니라 react 내부에서 필요로해서 요청하는것이다.

  ## TOC 내부에 로직을 직접 TOC.js에서 수정하지 않고, App.js에서 수정하고 싶다.?! 
- contents 추가했음
- TOC data={this.state.contents}
```jsx
App.js
class App extends Component {
constructor(props){
	super(props);
	this.state = { 
	subject:{title:'WEB', sub:'World Wid Web!'}
	contents: [
	{id:1, title:'HTML', desc: "HTML is for information"}
	{id:2, title:'CSS', desc: "CSS is for design"}
	{id:3, title:'Javascript', desc: "js is for interactive"}
	]
	}
}
render() { 
	return (
		<div className="App">
			<Subject 
				title={this.state.subject.title} sub="world wide web!">
				sub={this.state.subject.sub}>
			</Subject> 
			<TOC data={this.state.contents}></TOC>
			<Content title=HTML" desc="HTML is HyperText Markup Language."></Content>
			</div>
			);
			}
}
```

```jsx
TOC.js
render() { 
var lists = [];
var data = this.props.data;
var i =0;
while(i < data.length)
{
lists.push(<li key={data[i].id})><a herf="/content/"+data[i].id>{data[i].title}</a></li>
i = i+1;
}
return 
<nav> 
	<ul>
		{lists}
	</ul>
</nav>	
}
}
```

- 부모인 App입장에서는 state 내부정보를 사용했고, 그것을 전달할때는 props로 전달했음. 
- App 입장에서는  data라는 props만 알면 된다.
  <TOC data = {this.state.contents}> 는 prps이다.