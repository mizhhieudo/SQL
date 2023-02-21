
## Left join

### Define 

"Left join" là một thuật ngữ trong cơ sở dữ liệu, được sử dụng để kết hợp hai bảng dữ liệu trên một hoặc nhiều cột chung, và lấy ra tất cả các hàng trong bảng trái (left table), cộng với các hàng trong bảng phải (right table) mà có giá trị khớp với các hàng trong bảng trái. Nếu không có bất kỳ hàng nào trong bảng phải khớp với các hàng trong bảng trái, các giá trị của bảng phải sẽ được đặt là NULL.
## Example 
Ví dụ về left join như sau:

Giả sử chúng ta có hai bảng "departments" và "employees" với cấu trúc dữ liệu như sau:

Bảng "departments":

|department_id|name|
|-|-|
|1|Sales|
|2|Marketing|
|3|Engineering| 
|4|Human Resources|

Bảng "employees":
|employee_id|name|department_id|
|-|-|-|
|1|John Smith	|1|
|2|Jane Doe	|2|
|3|Peter Jones	|1|
|4|Sarah Lee	|3|
|5|Michael Chen	|NULL|

Trong đó, bảng "employees" có một cột "department_id" để xác định phòng ban mà mỗi nhân viên đang làm việc, và có một hàng cuối cùng với giá trị NULL để đại diện cho một nhân viên không thuộc bất kỳ phòng ban nào.

Chúng ta muốn lấy tất cả các bộ phận cùng với các nhân viên tương ứng (nếu có), bao gồm cả những bộ phận không có nhân viên nào và nhân viên không thuộc bất kỳ bộ phận nào.

Chúng ta có thể sử dụng left join để làm điều đó như sau:

```sql
SELECT departments.name, employees.name
FROM departments
LEFT JOIN employees
ON departments.department_id = employees.department_id;
```
Kết quả của truy vấn này sẽ trả về bảng mới chứa tên của các bộ phận và tên của các nhân viên tương ứng (nếu có):

|name|name|
|-|-|
|Sales|John Smith|
|Sales|Peter Jones|
|Marketing|Jane Doe|
|Engineering|Sarah Lee|
|Human Resources	|NULL|

Như vậy, chúng ta đã sử dụng left join để lấy tất cả các bộ phận cùng với các nhân viên tương ứng (nếu có), bao gồm cả những bộ phận không có nhân viên nào và nhân viên không thuộc bất kỳ bộ phận nào.
