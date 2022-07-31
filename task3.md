# 作业3

## 任务：

**构建乘客类，至少包含如下内容：**

**属性：是否年满18岁，历史订单，未出行订单，**

**方法 ：订票，检票**

代码如下：

### Order类

```objective-c
//订单类
@interface Order:NSObject()
{
    NSDate* date;//出发日期
    NSString* flight;//航班
    NSSTring* dest;//到达站点
    BOOL* checked;//是否检票
    BOOL* changed;//是否改签过
}
@property(nonatomic,strong) NSDate*date;
@property(nonatomic,strong) NSString*flight;
@property(nonatomic,strong) NSString*dest;

-(void)book_ticket:(NSDate*)date:(NSString*)flight:(NSString*)dest;//订票
-(void)endorse_ticket:(NSDate*)date:(NSString*)flight:(NSString*)dest;//改签
-(void)check_ticket:(NSString*)fli:(float)tim:(NSString*)dat;//检票
@end
@implementation Order
//订票
-(void)book_ticket:(NSDate*)dat:(NSString*)fli:(NSString*)des
{
    date=dat;
    flight=fli;
    dest=des;
    checked=NO;
    changed=NO;
    NSLog(@"The flight %@ will leave on %@ and arrive in %@",fli,dat,des);
}
//改签
-(void)endorse_ticket:(NSDate*)date:(NSString*)flight:(NSString*)dest
{
    if(changed=YES)
    {
        NSLog(@"The flight %@ couldn't be endorsed twice",fli);
        return 0;
    }
    date=dat;
    flight=fli;
    dest=des;
    checket=NO;
    changed=YES;
    NSLog(@"The flight after endoresing will leave on %@ and arrive in %@",fli,dat,des);
}
//检票
-(void)check_ticket:(NSString*)fli:(float)tim:(NSString*)dat
{
    checked=YES;
    NSLog(@"The ticket of flight %@ was checked at %f on %@",fli,tim,dat);
}
@end
```

------

### Person类

```objective-c
//公民类
@interface Person:NSObject()
{
    NSString* name;
    NSString* nation;
    NSString* address;
    int age;
    NSNumber* idnumber;
    NSNumber* telnumber;
}
@property(nonatomic,strong) NSString*name;
@property(nonatomic,strong) NSString*nation;
@property(nonatomic,strong) NSString*address;
@property(nonatomic,strong) int age;
@property(nonatomic,strong) NSNumber*idnumber;
@property(nonatomic,strong) NSNumber*telnumber;
@end
@implementation Person
- (instancetype)initWithName:(NSString*)nam nation:(NSString*)nati address:(NSString*)add idnumber:(NSNumber*)idn
{
    if(self=[super init])
    {
        [self createPersonWithName:nam nation:nati address:add idnumber:idn];
    }
    return self;
}
-(void)createPersonWithName:(NSString*)nam nation:(NSString*)nati address:(NSString*)add idnumber:(NSNumber*)idn
{
    self.name=nam;
    self.nation=nati;
    self.address=add;
    self.idnumber=idn;
    [self fetchIDWithAddress:adress completion:(^NSNumber*number)
     {
         self,idNumber=nunmber;
     }];
}
@end
```

------

### Passenger类

```objective-c
//乘客类
@interface Passenger:Person()
{
    BOOL* adult;//是否成年
    NSMutableArray* his_order=[NSMutableArray array];//历史订单
    NSMutableArray* untra_order=[NSMutableArray array];//未出行订单
}
-(void)add_order:(Order*)order;//添加订单
-(void)cancellation:(Order*)order;//取消订单
@end
    
@implementation Passenger
//预定订单
-(void)add_order:(Order*)order
{
    [his_order addObject:order];
    [untra_order addObject:order];
}
//取消订单
-(void)cancellation:(Order*)order
{
    [untra_order removeLastObject];
}
@end
```

