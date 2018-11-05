# ECMAScript 
ES6 là chữ viết tắt của ECMAScript 6, đây được coi là một tập hợp các kỹ thuật nâng cao của Javascript và là phiên bản mới nhất của chuẩn ECMAScript.

- Block - Scoped Constructs Let and Cont: khai báo biến tạm thời bằng `let` biến này sẽ chỉ có giá trị trong block `{ }`
    ```
    var a = 10;
    for(let i =0; i<4; i++){
        a += i;
    }
    ```
- Arrow Function: khai báo hàm bằng `=>`
    ```
    #hàm thông thường
    var hello = (name, message) => {
        console.log('Hello '+ name);
        console.log(message);
    };
    
    #hàm chỉ 1 câu lệnh
    var hello = (name, message) => console.log('Hello '+ name + ', ' + message);
    
    #hàm 1 tham số 
    var hello = message => console.log(message);
    
    ```
- Destructuring Assignment: Tách các phần tử của Array hoặc Object thành nhiều biến chỉ bằng một đoạn code duy nhất
    ```
    #vd1
    var ar = [1,2,3];
    var [a,b,c] = ar;
    
    #vd2
    var ob = { a: 10, b: 11 }
    var { a: x, b: y} = ob;
    
    ```
- Default Parameters: gán giá trị mặc định của tham số khi truyền vào các function
    ```
    function abc(name='sinionth'){
        console.log(name);
    };
    ```
- Rest Parameter:khai báo một hàm với số lượng tham số không xác định
    ```
    function xyz(a,b, ...other){
        console.log(other);
    };
    ```
- Template Literals: hiển thị các biến trong chuỗi
    ```
    var first = "abc";
    var last = "xyz";
    var name = `Hello: ${first} ${last}.`
    ```
- Multi-line String: chuối nhiềm dòng
    ```
    var str = `
            1234567890
            qwerty
            asdfgh
            `
    ```
- Enhanced Object Literals: mô tả object một cách gọn gàng hơn
    - mặc định gán giá trị cho property khi property có tên match với tên của biến
        ```
        function createSinger (name, age, address, salary) {
          return { name, age, address, salary}
        }
        ```
    - set tên của property một cách linh hoạt hơn
        ```
        function createSinger (name, age, address, salary) {
            return {
                ['salaryOf' + name] : salary,
            }
        }
        ```
- Promises: giải quyết vấn đề bất đồng bộ
    ```
    var promise = new Promise(executor);
    #executor là 1 hàm có 2 tham số đầu vào là 2 hàm phản hồi resolve và reject.
    #Hàm resolve sẽ được gọi khi xử #lý thành công, còn reject sẽ được gọi khi xử lý thất bại.
    
    promise.then(...).catch(...)
    #trong then sẽ mô tả hành động khi executor xử lý thành công 
    ```
- Classes: OOP
    ```
    class Rectangle {
        constructor(height, width) {
            this.height = height;
            this.width = width;
        }
        
        get area() {
            return this.calcArea();
        }
        
        calcArea() {
            return this.height * this.width;
        }
    }
    const square = new Rectangle(10, 10);
    console.log(square.area);
    ```
