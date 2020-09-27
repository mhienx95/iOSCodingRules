# Coding Convention Swift


## 1. Naming
### 1.1 Đặt tên với vai trờ và mục đích rõ ràng dễ hiểu

Class, Method, và các biến instance ... đều cần được đặt tên với vai trò và mục đích rõ ràng. Các biến bên trong Method hoặc những biến sử dụng trong phạm vi hẹp thì có thể đặt tên ngắn gọn giản lược cũng được

### 1.2 Camel case

Class, Method sử dụng chữ hoa để bắt đầu, còn các method, biến, định nghĩa, case .. bắt đầu bằng chữ cái thường

## 2. Type
### 2.1 Khỉ sử dụng kiểu Optional → sử dụng if let / guard let / Nil Coalescing Operator (a ?? b)

`if_let`
```swift
if let unwrap = optional {
    // xử lý sau khi unwrap
} else {
    // xử lý khi unwrap thất bại
}
```
`guard`
```swift
guard let selected = tableView.indexPathsForSelectedRows else { return }
```
`Nil_Coalescing_Operator(a??b)`
```swift
func someMethod(intArray: [Int]?) {
    let value = intArray ?? [Int]()
    // xử lý gì đó ...
}
```
### 2.2 Khi sử dụng Downcast ta sử dụng `as?`
Không sử dụng `as!` trừ trường hợp các biến mà giá trị đầu bắt buộc phải nhập như các biến `IBOutlet` thì sử dụng `as!` cũng được
##3. Classes
###3.1 `self` được giản lược khi access vào các property và method

Xcode sử dụng màu sắc để phân biệt các biến local rồi nên ko cần sử dụng self nữa
###3.2 không cần định nghĩa `delegate` ở SubClass

Vì khi định nghĩa `delegate` ở Class mới, khó kiểm soát các vấn đề
###3.3 `ReadOnly` property không cần viết keyword `get`

Ta không cần viết `get` ở các property `ReadOnly` nữa nên có thể giản lược đi được

```swift
class SomeClass: NSObject {
    var base: Float = 10.0
    var twice: Float {
        return base * 2
    }
}
```

##4. Functions
###4.1 Khi định nghĩa Method, Label được giản lược

Về cơ bản thì Label sẽ được giản lược đi khi định nghĩa Method, UnderBar cũng không cần viết . Khi gọi hàm label được viết

```swift
// defenition
func someMethod(first: Bool, second: Int) {
    // do something
}

// call
someMethod(first: true, second: 10)
```

##5 Comments
HeaderComment giản lược

ClassHeader, MethodHeader được giản lược đi, với mục tiêu chỉ cần name là đã có thể hiểu được mục đích, vài trò trong Class, Method. Tuy nhiên nếu vẫn cần viết Header thì ta ko dùng `/* */` nữa mà sử dụng `///`

##6. Formating
###6.1 sau dấu phẩy cần có dấu cách (space)
```swift
let title = NSLocalizedString("someTitle", comment: "")
```
###6.2 Dấu hai chấm ở phần chỉ định kiểu , đằng trước không có dấu cách, đằng sau cần 1 dấu cách
```swift
let someNumber: Int = 10
```
###6.3 Ở câu lệnh điều khiển viết gộp lại 1 dòng thì ở trước và sau dấu "{" và dấu "}" cần một dấu cách

```swift
guard let unwrap = optional else { return }
```

##7. File Structures
`protocol` và `extension` về cơ bản nên được viết riêng sang file khác

##8. Tài liệu tham khảo
[raywenderlich/swift-style-guide](https://github.com/raywenderlich/swift-style-guide#protocol-conformance)
