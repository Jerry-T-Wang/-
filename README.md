# -
#利用if else 实现逻辑的闭合
def instruction():
    print("-" * 30)
    print("1 添加学生:")
    print("2 删除学生:")
    print("3 修改学生:")
    print("4 查询学生:")
    print("5 显示所有学生:")
    print("6 参看操作指南")
    print("0 退出系统.")
    print('-' * 30)
student=[]
instruction()
while True:
    print("^"*40)
    a=eval(input("输入操作数："))
    if a==1:
        l={}
        l["name"]=input("输入学生姓名")
        l["sex"]=input("输入学生性别")
        l["phone"]=input("输入学生手机号")
        student.append(l)
        print("^" * 40)
    elif a==2:
        if len(student) == 0:
            print("列表内无学生")
            continue
        delnum=eval(input("输入要删除的学生下标："))
        del student[delnum]
        print("删除完成！")
        print("^" * 40)
    elif a==3:
        if len(student) == 0:
            print("列表内无学生")
            print("请先进行添加")
            continue
        chnum=eval(input("输入要修改的学生下标！"))
        student[chnum]["name"]=input("输入修改后的学生姓名：")
        student[chnum]["sex"] = input("输入修改后的学生性别：")
        student[chnum]["phone"]=input("输入修改后的学生电话号码：")
        print("修改完成")
        print("^" * 40)
    elif a==4:
        if len(student) == 0:
            print("列表内无学生")
            continue
        str=input("输入要查询的学生姓名")
        tmp=0
        for i in range(len(student)):
            if student[i]["name"]==str:
                print(student[i])
            else:
                tmp+=1
        if tmp==len(student):
            print("抱歉，没有你要查找的这个人")
        print("^" * 40)
    elif a==5:
        if len(student) == 0:
            print("列表内无学生")
            continue
        num=len(student)
        for i in range(num):
            print(student[i])
        print("显示结束")
        print("^" * 40)
    elif a==6:
        instruction()
    else:
        break
