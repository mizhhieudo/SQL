## Inner Join

### Define 

"Inner join" là một thuật ngữ trong cơ sở dữ liệu, được sử dụng để kết hợp hai bảng dữ liệu trên một hoặc nhiều cột chung. Kết quả của inner join là một bảng mới, chỉ chứa các hàng mà có giá trị khớp trong cả hai bảng đầu vào.

### Example 
Giả sử chúng ta có hai bảng "employees" và "departments" với cấu trúc dữ liệu như sau:

Bảng "employees":

|employee_id|name|department_id|
|-|-|-|
|1|John Smith|1|
|2|Jane Doe|2
|3|Peter Jones | 1
|4|Sarah Lee|3

Bảng "departments":

|department_id|name|
|-|-|
|1|Sales|
|2|Marketing|
|3|Engineering|

Ta muốn kết hợp hai bảng này để lấy tên của nhân viên và tên của phòng ban tương ứng mà họ đang làm việc. Chúng ta có thể sử dụng inner join để làm điều đó như sau:
```sql
SELECT employees.name, departments.name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```
Kết quả của truy vấn này sẽ trả về bảng mới chứa tên của nhân viên và tên của phòng ban tương ứng mà họ đang làm việc:

|name|name|
|-|-|
|John Smith	|Sales|
|Jane Doe	|Marketing|
|Peter Jones|Sales|
|Sarah Lee	|Engineering|

Như vậy, chúng ta đã sử dụng inner join để kết hợp hai bảng dữ liệu trên cột chung "department_id" và lấy ra tên của nhân viên và tên của phòng ban tương ứng mà họ đang làm việc.