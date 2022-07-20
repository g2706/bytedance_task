# 作业2

## 任务：

**分别使用Objective-C和Swift来自定义一个Student类**

**属性：name(字符串)、major(字符串)、age(整型)**

**方法：study，有一个参数为time(浮点型)，表示学生学习了几个小时，打印出学习时间**

### 1.Objective-C

```objective-c
#import <Foundation/Foundation.h>
@interface Student//类的定义
{
    NSString* name;//实体属性变量，下同
    NSStirng* major;
    int age;
}
-(void)study:(float)time;//实例方法
@end
@implementation Student
-(void)study:(float)time
{
    NSLog(@"This student has studied %f hours",time);
}
@end
int main(int argc,const char* argv[])
{
    Student* hey=[[Student alloc] init];
    return 0;
}
```



### 2.Swift

```swift
import Cocoa
class Student
{
    var name:String
    var major:String
    var age:Int
    func study(time:Int)
    {
        print("This student has studied \(time)")
    }
}
let hey=Student(name:"sage",major:"software",age:19)
hey.study(5.6)
```

