1.变量/赋值

    ...arr的含义：扩展运算符 和 剩余运算符
2.函数
    箭头函数里arguments不可用
3.数组/json
    增加了7种 
        常见4种
                let a=[1,2,3,4,5,6]
            map :映射 1v1
                let b= a.map(item=>item>=3)
                return b

            filter: 过滤
                let c= a.filter(item=>item%2)
                return c

            forEach 遍历 不能用break
                let sum=0
                c.forEach(item=>{
                    sum+=item
                })
                return sum

            reduce 汇总 n >>> 1

                let e= a.reduce((tmp,item,index)=>{
                    if(index<a.length){
                        return tmp+item
                    }else{
                        return (tmp+item)/a.length
                    }
                })
                tem:遍历运算 第0个item被作为tmp初始值使用

            Array.form 遍历元素 将div类数组转化为数组
                let aDiv=document.getElementsByTagName("div");
                {
                    // aDiv.forEach(div=>{div.style.background="#f0f"})
                    // 不能执行 原因是aDiv是一个 类数组 array.like
                }
                Array.from(aDiv).forEach(div=>{div.style.background="#f0f"})
            改变数组的方法:
                pop()：删除数组最后一个元素，并返回该元素
                push()：在数组尾部添加元素，并返回更新后的数组长度
                shift()：删除数组的第一个元素，并返回该元素
                unshift()：在数组第一位添加元素，并返回更新后的数组长度
                sort()：对数组排序（按字符ASCII进行排序），也可添加回调函数按照想要的规则排序
                reverse()：数组反转
                splice(index, howmany, 新数据)：返回被删除元素所组成的数组
    
    json两种简写

        1.节点名字跟赋值变量的名字是一样的可以省略
        let json={a:a} >>> let json={a}
        2.json里的函数可以简写 function可以省略
        let json={a:a,show:function(){}} >>> let json={a,show()}
        
4.字符串
        字符串模板：`${json.name}`，可以折行
            let json={name:"jack",age:12}
            alert(`我叫${json.name},
            今年${json.age}岁`)
        startsWith(xxx) 以xxx开头
            let a=num.startsWith(135) 
        endsWith(xxx) 以xxx结尾
            let a=num.endsWith(456) 
5.面向对象
            class Person{
                constructor(name,age){
                    this.name=name;
                    this.age=age;
                }
                showName(){
                    alert(`我叫${this.name},我今年${this.age}岁`)
                }
            }
            let person=new Person("jack",12)
            // person.showName()
            
            class Worker extends Person{
                constructor(name,age,job){
                    super(name,age) //超类(父类) call apply
                    this.job=job
                }
                showJob(){
                    alert(`我是做${this.job}的`)
                }
            }

            let worker=new Worker("jack",12,"保洁")
            worker.showName()
            worker.showJob()



6.Promise
7.generator
8.模块
