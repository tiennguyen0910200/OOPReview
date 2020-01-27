OOP REVIEW
I.	4 tính chất của hướng đối tượng (có ví dụ và lợi ích khi sử dụng)
1.	Tính đóng gói
  -	Tính đóng gói :đóng gói thuộc tính và phương thức của đối tượng (hoặc lớp) thông qua việc giới hạn quyền truy cập giá trị của thuộc tính hoặc quyền gọi phương thức. Nói cách khác tính đóng gói cho phép kiểm soát quyền truy cập  giá trị của thuộc tính hoặc quyền gọi phương thức của đối tượng (hoặc lớp) và đối tượng (hoặc lớp) con.
  -	Ví dụ: 

public class Person ;
    private String cmnd;
    private String hoTen;

    public String getCmnd() {
        return cmnd;
    }
    public void setCmnd(String cmnd) {
        this.cmnd = cmnd;
    }
    public String getHoTen() {
        return hoTen;
    }
    public void setHoTen(String hoTen) {
        this.hoTen = hoTen;
    }
     
}

	public class TestPerson {
 
    public static void main(String[] args) {
        Person person = new Person();
        person.setHoTen("Trần Văn Bình");   
        person.setCmnd("212321678");
        System.out.println("Tên: " + person.getHoTen() + ", số cmnd: " + person.getCmnd());
    }
 
}
  -	Lợi ích: Giúp bảo mật dữ liệu, ngăn cản sự truy cập từ các lớp bên ngoài.
2.	Tính kế thừa
  -	Tính kế thừa: 1 lớp có thể thừa hưởng lại những thuộc tính, phương thức từ 1 lớp khác và sử dụng chúng như là của bản thân mình.
  -	Ví dụ:  Lớp TamGiacCan kế thừa lại lớp TamGiac để có thể sử dụng lại các thông tin như toạ độ 3 điểm A, B, C mà không cần phải khai báo.
  -	Lợi ích: 
     Cho phép chia sẽ các thông tin chung nhằm tái sử dụng và đồng thời giúp ta dễ dàng nâng cấp, dễ dàng bảo trì.
     Cho phép xây dựng 1 lớp mới từ lớp đã có.
3.	Tính trừu tượng 
   -	Trừu tượng vẫn có tồn tại, vẫn là một lớp thôi. Nhưng nó trừu tượng ở chỗ, nó không thể được dùng để tạo ra các đối tượng như những lớp bình thường khác. Lớp Trừu tượng khi này chỉ là cái “xác không hồn”, hay bạn có thể hiểu nó chỉ là một cái sườn, để mà bạn có thể tạo ra các lớp con của nó dựa vào sự ràng buộc từ cái sườn này.
   -	Ví dụ: 
Animal là 1 abstract class có phương thức abstract makeSound(), bởi vì Animal chưa thể cụ thể đc kà nó makeSound() như thế nào nên nó là abstract
   -	Lợi ích: nó lại ràng buộc các lớp con của nó buộc phải hiện thực nội dung cho các phương thức Trừu tượng bên trong nó
4.	Tính đa hình  
   -	Đa hình được xem như một đối tượng đặc biệt vì có lúc đối tượng này trở thành một đối tượng khác và cũng có lúc đối tượng này trở thành một đối tượng khác nữa.
   -	Ví dụ: Animal vs Dog, Animal có method makeSound() trả về là "Hello", Dog kế thừa đến Animal và makeSound() trả về là: "Go Go Go".
   -	Lợi ích: tăng khả năng tái sử dụng những đoạn mã nguồn được viết một cách tổng quát và có thể thay đổi cách ứng xử một cách linh hoạt tùy theo loại đối tượng.
5.	Lợi ích của việc sử dụng đối tượng
   -	Dễ dàng mở dự án ra rộng hơn. Dễ dàng quản lý code khi có sự thay đổi . Có tính bảo mật và tính tái sử dụng cao.
6.	Khi nào ta sử dụng Abstract class
   -	Khi muốn định nghĩa một đối tượng có những chức năng A,B,C trong đó tính năng A,B chắc chắn sẽ thực thi theo cách nào đó, còn tính năng C phải tùy thuộc vào đối tượng cụ thể là gì, ví dụ như đối tượng Dog, Cat chúng đều có 2 tai và 4 chân nhưng âm thanh tiếng kêu của chúng là khác nhau, Khi đó ta tạo 1 abstract class Animal có trường tai, chân và 1 abstract method makeSound()để lớp Dog kế thừa và override lại method makeSound() trả về Go Go còn Cat trả về Meow Meow
7.	Khi nào sử dung Interface
   -	Khi muốn xây dựng một bộ khung chuẩn gồm các chức năng mà các lớp phải follow theo
8.	Override là gì (đưa ra ví dụ)
   -	được định nghĩa là ghi đè 1 hoặc nhiều phương thức, có nghĩa là khi một lớp con kế thừa trực tiếp từ một lớp cha thì lớp con đó có thể định nghĩa lại một phương thức đã có trong lớp cha cho phù hợp với mục đích của nó.
   -	Ví dụ: lớp Animal có method makeSound()lớp con kế thừa từ Animal cx định nghĩa lại method makeSound ()
9.	Overload là gì (đưa ra ví dụ)
   -	được định nghĩa là nạp chồng phương thức, có nghĩa là nếu trong một lớp có nhiều phương thức cùng tên nhưng:
        +Khác nhau về số đối số truyền vào và các đối số có cùng kiểu dữ liệu.
        +Có cùng số đối số truyền vào và các đối số không có cùng kiểu dữ liệu. 
        +Khác nhau trình tự kiểu dữ liệu của các đối số.

   -	Ví dụ: public void getTotal(int a, int b, int c){ 
 s.o.p("A");
} 
public void getTotal(int a){ 
S.o.p("B");}
10.      Các access modifier trong java, khi dùng nó thì quyền truy cập sẽ như thế nào

   -  Private: thuộc tính đó sẽ không được phép truy cập, hay chỉnh sửa từ các lớp khác, trừ khi bạn xây dựng các phương thức getter và setter cho thuộc tính đó ,chỉ được truy cập trong cùng 1 class.
   -  Protected: Khả năng này mang ý nghĩa bảo vệ các giá trị của lớp cho các lớp con của nó dùng lại hoặc ghi đè. Do đó có thể hiểu, khả năng protected sẽ trao quyền sử dụng hoàn toàn tự do cho các lớp con, dù có ở cùng hay khác package. Khả năng này chỉ giới hạn với các lớp không phải lớp con của nó và nằm ngoài package mà thôi.
   -  Default: truy cập trong cùng một package
   -  Public: tất cả các lớp nào khác đều có thể truy xuất đến các giá trị này.
:



Sousecode: https://freetuts.net/tinh-dong-goi-encapsulation-trong-java-1125.html https://www.codehub.vn/PHP-Object-Oriented-Programming/Tinh-Dong-Goi,https://yellowcodebooks.com/2017/09/26/java-bai-32-tinh-truu-tuong-abstraction/,https://freetuts.net/tinh-da-hinh-polymorphism-trong-java-1134.html,https://freetuts.net/overriding-va-overloading-trong-java-1141.html,https://yellowcodebooks.com/2017/08/11/java-bai-25-kha-nang-truy-cap-vao-cac-gia-tri-lop/.
