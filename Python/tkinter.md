# 목차

---

## 1. 기본 프레임

```python
from tkinter import *

root = Tk()
root.title("Nad")
root.geometry("500x600+300+100") # 가로 * 세로 + x좌표 + y좌표

root.resizable(False, False) # x너비, y너비 변경 여부


root.mainloop()
```

* tkinter라는 모듈을 통해 파이썬으로 GUI를 구축할 수 있다.

---

## 2. 버튼

```python
from tkinter import *

# 위젯 = 상호작용할 수 있는 수많은 도구?(버튼, 체크박스, 텍스트 박스)

root = Tk()
root.title("Nad")
root.geometry("500x600")

btn1 = Button(root, text = "버튼1")
btn1.pack() # .pack == .blit

btn2 = Button(root, padx = 5, pady = 10, text = "버튼2222222222222") # 버튼의 크기 조정 (변동)
btn2.pack() 
btn3 = Button(root, padx = 10, pady = 5, text = "버튼3")
btn3.pack() 

btn4 = Button(root, width=10, height=3, text = "버튼444444444444444")
# 버튼의 크기 조정 (고정)
btn4.pack()

btn5 = Button (root, fg = "red", bg = "yellow", text = "버튼5")
btn5.pack()

photo = PhotoImage (file = "gul_basic/image.png")
btn6 = Button(root, image = photo)
btn6.pack()

def btncmd():
    print ("버튼이 눌렸어!")

btn7 = Button(root, text="동작하는 버튼", command = btncmd)
btn7.pack()


root.mainloop()
```

* 위젯을 선언할 때 속성값을 조정할 수 있음.
* pack()을 사용해야만 화면에 구현.

---

## 3. 라벨

```python
from tkinter import *

# label : 단순하게 글자나 이미지를 보여주는 역할을 한다. html의 div, span? 

root = Tk()
root.title("d")
label1 = Label(root, text = "안넝혀사에")
label1.pack()

photo = PhotoImage(file="gul_basic/image.png")
label2 = Label(root, image = photo)
label2.pack()

# .config : 속성 수정
# 함수 내에서 label의 이미지 값을 바꾸려면 photo 값을 전역 변수 선언 해줘야함

def change():
    label1.config(text="안 안녕하세요")
    global photo1
    photo1 = PhotoImage(file ="gul_basic/image1.png")
    label2.config(image=photo1)

btn = Button(root, text="클릭", command=change)
btn.pack()

root.mainloop()
```

* 텍스트를 표기한다.
* 함수 내에서 label의 이미지 값을 바꾸려면 PhotoImage를 담을 변수를 전역 변수로 선언 해줘야 한다.

---

## 4. 텍스트 상자

```python
from tkinter import *

# Text : 텍스트 위젯을 생성한다.

root = Tk()
root.title("d")
root.geometry("640x480")

txt = Text(root, width=30, height=5)
txt.pack()

txt.insert(END, "insert text")

# Entry : 한 줄 짜리 텍스트 위젯을 생성한다.

e = Entry(root, width = 30)
e.pack()
e.insert(0, "한 줄만 입력")

def btncmd():
    # 입력
    print(txt.get("1.0", END)) # 처음부터 끝까지 있는 모든 걸 가져와라 | 1 : 첫번 째 line을 가져와라 / 0 : column(인덱싱) 기준으로 맨 왼 쪽부터 가져와라
    print (e.get())

    # 출력
    txt.delete("1.0", END)
    e.delete(0, END)

btn = Button(root, text="글릭", command = btncmd)
btn.pack()

root.mainloop()
```

* `insert`로 초기값을 설정할 수 있다.
* `Entry`는 한 줄 짜리 위젯을 생성한다.
* `.get`으로 변수의 값을 가져올 수 있다.
* `.delete`로 텍스트 위젯을 지울 수 있다.

---

## 5. 리스트 박스

```python
from tkinter import *

# ListBox : 여러 줄에 걸쳐서 목록을 관리하는 위젯

root = Tk()
root.title("d")
root.geometry("640x480")

listbox = Listbox(root, selectmode="extended", height=0) # selectmode - single : 하나만 선택, extended : 중복 선택 | height - 0 : 전체 보기, n : n개만큼의 목록
listbox.insert(0, "사과")
listbox.insert(1, "딸기")
listbox.insert(2, "qlrenf")
listbox.insert(END, "dsad")
listbox.insert(END, "dsa\\xzcvd")
listbox.pack()

def btncmd():
    # 삭제
    # listbox.delete(END)

    # 갯수 확인
    # print ("리스트에는", listbox.size(), "개가 있어요")

    # 항목 확인 (get. (시작 idx, 끝 idx))
    # print ("1번째부터 3번째까지의 항목 : ", listbox.get(0, 2))

    # 선택된 항목 확인 (위치로 반환)
    print ("선택된 항목 : ", listbox.curselection())

btn = Button(root, text="삭제", command = btncmd)
btn.pack()

root.mainloop()
```

* `Listbox`로 여러 줄의 목록을 관리하는 위젯을 생성할 수 있다.
* `insert`로 목록 삽입, `delete`로 목록 제거.
* `curselection`은 선택된 항목을 인덱싱해서 반환한다.

---

## 6. 체크박스

```python
from tkinter import *

# Checkbutton : 각 항목을 체크, 체크 해제 할 수 있다.

root = Tk()
root.title("d")
root.geometry("640x480")
IntVar
chkvar = IntVar() # checkvar 에 int 형으로 값을 저장한다.

chkbox = Checkbutton(root, text="오늘 하루 보지 않기", variable=chkvar)
chkbox.select()
chkbox.deselect()
chkbox.pack()

chkvar2 = IntVar()
chkbox2 = Checkbutton(root, text="일주일 동안 보지 않기", variable = chkvar2)
chkbox2.pack()


def btncmd():
   print (chkvar.get()) 
   print (chkvar2.get())
btn = Button(root, text="삭제", command = btncmd)
btn.pack()

root.mainloop()
```

* 체크박스의 체크 여부(0, 1)를 저장할 변수를 필요로 한다.

---

## 7. 라디오버튼

```python
from tkinter import *

# Radiobutton : 여러 체크 박스 중 하나를 선택할 수 있다 

root = Tk()
root.title("d")
root.geometry("640x480")
Label(root, text="메뉴를 선택하시오.").pack()

burger_var = IntVar() # int 형으로 값을 저장한다.
btn_burger1 = Radiobutton(root, text="햄버거", value=1, variable=burger_var)
btn_burger1.select()
btn_burger2 = Radiobutton(root, text="치즈버거", value=2, variable=burger_var)
btn_burger3 = Radiobutton(root, text="햄거", value=3, variable=burger_var)

btn_burger1.pack()
btn_burger2.pack()
btn_burger3.pack()


drink_var = StringVar()
btn_drink1 = Radiobutton(root, text="콜라", value="콜라", variable=drink_var)
btn_drink1.select()
btn_drink2 = Radiobutton(root, text="사이다", value="사이다", variable=drink_var)

btn_drink1.pack()
btn_drink2.pack()

def btncmd():
    print (burger_var.get()) # 햄버거 중 선택된 라디오 항목의 값(value)를 출력
    print (drink_var.get()) # 음료 중 선택한 라디오 항목의 값(value)를 출력
    
btn = Button(root, text="주문", command = btncmd)
btn.pack()

root.mainloop()
```

* 라디오박스의 값(value)을 저장할 변수를 필요로 한다.

---

## 8. 콤보 박스

```python
import tkinter.ttk as ttk
from tkinter import *

# combobox : 여러 목록 중 하나를 선택

root = Tk()
root.title("d")
root.geometry("640x480")
Label(root, text="메뉴를 선택하시오.").pack()

values = [str(i) + "일" for i in range(1, 32)]
combobox = ttk.Combobox(root, height=5, values=values, state="")
combobox.pack()
combobox.set("카드 결제일") # 최초 목록 제목 설정

readonly_combobox = ttk.Combobox(root, height=0, values=values, state="readonly") # 읽기 전용
readonly_combobox.current(0)
readonly_combobox.pack()

def btncmd():
    print (combobox.get())
    print (readonly_combobox.get())
    
btn = Button(root, text="주문", command = btncmd)
btn.pack()

root.mainloop()
```

* 콤보 박스를 사용하려면 `tkinter.ttk`라는 모듈이 추가로 필요하다.
* 위젯의 값이 수정되지 않게 하려면 `state="readonly"`.

---

## 9. 프로그래스 바

```python
import tkinter.ttk as ttk
from tkinter import *
import time

# Progressbar : 진척도를 나타내는 막대

root = Tk()
root.title("d")
root.geometry("640x480")
Label(root, text="메뉴를 선택하시오.").pack()

# progressbar = ttk.Progressbar(root, maximum=100, mode="indeterminate")
# progressbar1 = ttk.Progressbar(root, maximum=100, mode="determinate")
# progressbar.start(10)
# progressbar1.start(10)
# progressbar.pack()
# progressbar1.pack()

p_var2 = DoubleVar()
progressbar2 = ttk.Progressbar(root, maximum=100, length=150, variable=p_var2)
progressbar2.pack()

def btncmd():
    for i in range(1, 101):
        time.sleep(0.1) # 대기

        p_var2.set(i)
        progressbar2.update()
        print (p_var2.get())
        if p_var2.get() == 50:
            print ("절반 경과")
        


btn = Button(root, text="시작", command = btncmd)
btn.pack()

root.mainloop()
```
* `variable`에 해당하는 변수로 바를 처음부터 끝까지 가게끔 할 수 있다.
* 반복문 안에 `update`를 넣어야 변수값이 제대로 변동된다.

---

## 10. 메뉴

```python
from tkinter import *


# Menu

root = Tk()
root.title("tkinter로 만드는 GUI")
root.geometry("640x480")

def create_new_file():
    print ("새 파일 생성")

menu = Menu(root)

# File 메뉴
menu_file = Menu(menu, tearoff=0)
menu_file.add_command(label="New file", command=create_new_file)
menu_file.add_command(label="New Window")
menu_file.add_separator()
menu_file.add_command(label="open File...")
menu_file.add_separator()
menu_file.add_command(label="Save All", state="disable")
menu_file.add_separator()
menu_file.add_command(label="Exit", command=root.quit)

menu.add_cascade(label="File", menu=menu_file)

# Edit 메뉴 (빈 값)
menu.add_cascade(label="Edit")

# Language 메뉴 추가 (radio 버튼을 추가)
menu_lang = Menu(menu, tearoff=0)
menu_lang.add_radiobutton(label="Python")
menu_lang.add_radiobutton(label="Java")
menu_lang.add_radiobutton(label="C++")
menu.add_cascade(label="Language", menu=menu_lang)

# View 메뉴
menu_view = Menu(menu, tearoff=0)
menu_view.add_checkbutton(label="Show map")
menu_view.add_checkbutton(label="Show Stack")
menu_view.add_radiobutton(label="Solo")
menu_view.add_radiobutton(label="Duo")
menu.add_cascade(label="View", menu=menu_view)

menu_file.add_separator()



root.config(menu=menu)
 
root.mainloop()
```

* cascade의 속성값 menu에 add_command로 항목이 추가된 변수를 넣음으로써 실제 메뉴창처럼 구현할 수 있다. See

---

## 11. 메세지 박스

```python
import tkinter.messagebox as msgbox
from tkinter import *


# Messagebox

root = Tk()
root.title("tkinter로 만드는 GUI")
root.geometry("640x480")

def info():
    msgbox.showinfo("알림", "404 Not Found")

def warn():
    msgbox.showinfo("경고", "warning!")

def error():
    msgbox.showerror("에러", "holymoly...")

def okcancel():
    msgbox.askokcancel("여부", "serious?")

def retrycancel():
    msgbox.askretrycancel("재시도", "일시적 오류")


def yesno():
    msgbox.askyesno("예스노", "바밤!")

def yesnocancel():
    check(msgbox.askyesnocancel("","dd"))
    
def check(response):
    if response == 1:
        print ("예")
    elif response == 0:
        print ("아니오")
    else:
        print ("취소")

Button(root, command=info, text="버튼").pack()

Button(root, command=warn, text="테스트").pack()

Button(root, command=error, text="에러").pack()

Button(root, command=okcancel, text="취소").pack()

Button(root, command=retrycancel, text="재시도").pack()

Button(root, command=yesno, text="예아니오").pack()

Button(root, command=yesnocancel, text="예스노취소").pack()
 
root.mainloop()
```

* showinfo, showerror, askokcancel, askretrycancel, askyesno, askyesnocancel 같은 여러 종류의 메세지 창을 만들 수 있다.

---

## 12. 프레임

```python
from tkinter import *


# Messagebox

# 메뉴 프레임
root = Tk()
root.title("tkinter로 만드는 GUI")
root.geometry("640x480")

Label(root, text="메뉴 선택하라우!").pack(side="top")

Button (root, text="주문하기").pack(side="bottom")

frame_burger = Frame(root, relief="solid", bd = 3)
frame_burger.pack(side="left", fill="both", expand=True)

Button(frame_burger, text="햄버거").pack()
Button(frame_burger, text="햄버거").pack()
Button(frame_burger, text="햄버거").pack()

# 음료 프레임
frame_drink = LabelFrame(root, text="음료")
frame_drink.pack(side="right", fill="both", expand=True)
Button(frame_drink, text="콜라").pack()
Button(frame_drink, text="펩시").pack()

root.mainloop()
```

* Frame으로 구역을 조절할 수 있다.

---

## 13. 스크롤 바

```python
from tkinter import *


# Messagebox

# 메뉴 프레임
root = Tk()
root.title("tkinter로 만드는 GUI")
root.geometry("640x480")

frame = Frame(root)
frame.pack()

scrollbar = Scrollbar(frame)
scrollbar.pack(side="right", fill="y")

# set이 없으면 스크롤을 내려도 다시 올라옴
listbox = Listbox(frame, selectmode="extended", height=10, yscrollcommand=scrollbar.set)

for i in range(1, 32):
    listbox.insert(END, str(i)+"일")

scrollbar.config(command=listbox.yview)

listbox.pack()
root.mainloop()
```

* Scrollbar와 그에 대응할 위젯을 연결시켜야 정상 작동한다. (yscrollcommand=scrollbar.set, command=listbox.yview)

---

## 14. 그리드

```python
from tkinter import *


# Messagebox

# 메뉴 프레임
root = Tk()
root.title("tkinter로 만드는 GUI")
root.geometry("640x480")

# btn1 = Button(root, text='Button 1')
# btn2 = Button(root, text='Button 2')

# btn1.pack()
# btn2.pack()

# btn1.pack(side="left", fill="y")
# btn2.pack(side="right", fill="y")

# btn1.grid(row=0, column=0)
# btn2.grid(row=1, column=1)

btn_f16 = Button(root, text="f16", width=5, height=2)
btn_f17 = Button(root, text="f17", width=5, height=2)
btn_f18 = Button(root, text="f18", width=5, height=2)
btn_f19 = Button(root, text="f19", width=5, height=2)


btn_f16.grid(row=0, column=0, sticky=N+E+W+S, padx=3, pady=3) 
btn_f17.grid(row=0, column=1, sticky=N+E+W+S, padx=3, pady=3)
btn_f18.grid(row=0, column=2, sticky=N+E+W+S, padx=3, pady=3)
btn_f19.grid(row=0, column=3, sticky=N+E+W+S, padx=3, pady=3)

btn_clear = Button(root, text="clear", width=5, height=2)
btn_equal = Button(root, text="=", width=5, height=2)
btn_div = Button(root, text="/", width=5, height=2)
btn_mul = Button(root, text="*", width=5, height=2)

btn_clear.grid(row=1, column=0, sticky=N+E+W+S, padx=3, pady=3) 
btn_equal.grid(row=1, column=1, sticky=N+E+W+S, padx=3, pady=3)
btn_div.grid(row=1, column=2, sticky=N+E+W+S, padx=3, pady=3)
btn_mul.grid(row=1, column=3, sticky=N+E+W+S, padx=3, pady=3)

btn_7 = Button(root, text="7", width=5, height=2)
btn_8 = Button(root, text="8", width=5, height=2)
btn_9 = Button(root, text="9", width=5, height=2)
btn_sub = Button(root, text="-", width=5, height=2)

btn_7.grid(row=2, column=0, sticky=N+E+W+S, padx=3, pady=3) 
btn_8.grid(row=2, column=1, sticky=N+E+W+S, padx=3, pady=3)
btn_9.grid(row=2, column=2, sticky=N+E+W+S, padx=3, pady=3)
btn_sub.grid(row=2, column=3, sticky=N+E+W+S, padx=3, pady=3)

btn_4 = Button(root, text="4", width=5, height=2)
btn_5 = Button(root, text="5", width=5, height=2)
btn_6 = Button(root, text="6", width=5, height=2)
btn_add = Button(root, text="+", width=5, height=2)

btn_4.grid(row=3, column=0, sticky=N+E+W+S, padx=3, pady=3) 
btn_5.grid(row=3, column=1, sticky=N+E+W+S, padx=3, pady=3)
btn_6.grid(row=3, column=2, sticky=N+E+W+S, padx=3, pady=3)
btn_add.grid(row=3, column=3, sticky=N+E+W+S, padx=3, pady=3)

btn_1 = Button(root, text="1", width=5, height=2)
btn_2 = Button(root, text="2", width=5, height=2)
btn_3 = Button(root, text="3", width=5, height=2)
btn_enter = Button(root, text="enter", width=5, height=2)

btn_1.grid(row=4, column=0, sticky=N+E+W+S, padx=3, pady=3) 
btn_2.grid(row=4, column=1, sticky=N+E+W+S, padx=3, pady=3)
btn_3.grid(row=4, column=2, sticky=N+E+W+S, padx=3, pady=3)
btn_enter.grid(row=4, column=3, rowspan=2, sticky=N+E+W+S, padx=3, pady=3)

btn_0 = Button(root, text="0", width=5, height=2)
btn_point = Button(root, text=".", width=5, height=2)

btn_0.grid(row=5, column=0, columnspan=2, sticky=N+E+W+S, padx=3, pady=3) 
btn_point.grid(row=5, column=2, sticky=N+E+W+S, padx=3, pady=3)

root.mainloop()
```

* grid로 좌표평면 상에서 위젯을 배치할 수 있다.

---
