> 利用递归 把patientId转换成chidren
```js
function toTreeFn(arr) {
    const result = []
    const obj = {}
    arr.forEach(item => {
        obj[item.id] = item
    })
    arr.forEach(item => {
        // item.pid 为" "时 返回underfined
        const parent = obj[item.patientId]
        if (parent) {
            (parent.children || (parent.children = [])).push(item)
        } else {
            // 这里push的item是pid为undefined的数据
            result.push(item)
        }
    })
    return result
}
```