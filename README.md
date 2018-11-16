# deepClone
deepClone
```
deepClone(obj){
      let util = ( ()=> {
        // 获取数据类型
        let getType=(obj)=> {
          let type = Object.prototype.toString.call(obj);
          return /object\s(.*)]/.exec(type)[1];
        };
        let isType=(obj, type)=>{
          obj = getType(obj).toLowerCase();
          return obj === type;
        };
      return {isType: isType}})();
      // 若不是对象类型或是null类型，直接输出
      if (typeof obj !== 'object' || obj === null) {
          return obj
      }
      let i;
      // 根据目标是Array类型还是object来设置目标参数的类型
      let target = util.isType(obj, 'array') ? [] : {};
      for (i in obj) {
          // 判断当前复制的对象是否为对象类型数据
          if (typeof obj[i] === 'object') {
              this.deepCopy(obj[i]);
          }
          target[i] = obj[i]
      }
      return target  ;
    },
```
