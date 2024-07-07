# map 基础使用

\***_Map 是一组键值对的结构，用户解决以往不能用对象作为键的问题_**

1.可以接受一个数组作为参数，该数组成员是一个表示键值对的数组
特点：极快的查找速度，函数对象基本类型都可以作为键值对

      let m = new Map([
        ["user", "user111111"],
        ["student", "student111111"],
      ]);
      m.set("teacher", "teacher12312321").set("teacher111"); // 2.使用set方法添加元素，支持链式操作
      //   console.log(m);
      //   console.log(m.get("user"));
      // 3.对于键是对象的Map， 键保存的是内存地址，值相同但内存地址不同的视为两个键。
      let arr = ["xiexie"];
      m.set(arr, 12321);
      //   console.log(m.get(arr)); // 对象是引用类型，当对象作为map键的时候，必须使用当前对象
      //   console.log(m.get(["xiexie"])); // undefined 这样是无法获取
      // 4.获取数量
      console.log(m.size);
      // 5.元素检测
      console.log(m.has(arr));
      // 6.删除元素
      //   m.delete(arr);
      //   console.log(m.has(arr));
      // 7.清空map集合
      //   m.clear();
      //   console.log(m.size);
      // 8.快速遍历数据
      //   console.log(m.keys());
      //   console.log(m.values());
      //   console.log(m.entries());
      // 9.使用for of遍历map数据
      for (const [key, value] of m) {
        // console.log(123, key, value);
      }
      // 10.数组转换，可以使用展开语法（...）或者Array.from静态方法将map类型转换为数组
      console.log([...m]); // [Array(2), Array(2), Array(2), Array(2), Array(2)]
      console.log(Array.from(m)); // [Array(2), Array(2), Array(2), Array(2), Array(2)]
