# Hooks

## 为什么要使用 hooks

1.函数式组件拥有比类组件更好**逻辑性**，方便提取公共方法和组件；
2.函数式编程的写法代码量少，**效率高**；
3.**性能**更好。

## Hooks 的使用

### useState

作用：存储数据，派发更新。

### useEffect

作用：生命周期函数——componentDidMount、componentwillreciveprops、componentDidUpdate、componentWillUnmount

```js
usefect(function,array)
```

异步函数：

```js
async function fetchMyAPI() {
  let response = await fetch('api/data')
  response = await res.json()
  dataSet(response)
}

useEffect(() => {
  fetchMyAPI();
}, []);
```

### useLayoutEffect

Dom绘制之前完成回调函数

### useRef

缓存Dom节点

```js
const DemoUseRef = ()=>{
    const dom= useRef(null)
    const handerSubmit = ()=>{
        /*  <div >表单组件</div>  dom 节点 */
        console.log(dom.current)
    }
    return <div>
        {/* ref 标记当前dom节点 */}
        <div ref={dom} >表单组件</div>
        <button onClick={()=>handerSubmit()} >提交</button> 
    </div>
}
```

储存改变数据：
相比于useState存储数据，useRef不会被销毁，可以一直使用。

### useContext

组件传值

### useMemo

作用：减少因为组件更新而导致的函数重复执行。

### useCallback

作用：储存传递给

## Hook规则

1.只在最顶层使用 Hook，不要在循环，条件或嵌套函数中调用 Hook
    因为hooks在react中类似数组的形式储存，一旦被创建，hooks的顺序就确定了。之后每一次读取hooks中存储的值都会按照顺序进行索引。如果某个hooks是在条件语句中，当它缺失的时候，react并不知道，所以下一个hooks会把未执行的hooks值返回。

## 自定义Hooks
