---
title: "nameof (справочник по C#)"
ms.date: 2017-06-16
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- nameof_CSharpKeyword
- nameof
dev_langs:
- CSharp
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: db79af5f38439b881863cf3e03aa0e684ec5cd39
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="nameof-c-reference"></a>nameof (справочник по C#)

Используется для получения простого (неполного) строкового имени переменной, типа или члена.  

При сообщении об ошибках в коде, подключении к ссылкам "модель — представление — контроллер" (MVC), запуске при событиях изменения свойств и т. д. часто требуется записать строковое имя метода.  `nameof` позволяет поддерживать код допустимым при переименовании определений.  Раньше приходилось использовать строковые литералы для ссылки на определения, что значительно усложняло работу при переименовании элементов кода, так как инструменты не могут проверять такие строковые литералы.  
  
 Выражение `nameof` имеет следующую форму:  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a>Основные варианты использования  
 В следующих примерах показаны основные варианты использования для `nameof`.  
  
 Проверка параметров:  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 Ссылки на действия MVC:  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 INotifyPropertyChanged:  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 Свойство зависимости XAML:  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 Ведение журнала:  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 Атрибуты:  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a>Примеры  
 Некоторые примеры на C#:  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
nameof(C) -> "C"  
nameof(C.Method1) -> "Method1"   
nameof(C.Method2) -> "Method2"  
nameof(c.Method1) -> "Method1"   
nameof(c.Method2) -> "Method2"  
nameof(z) -> "z" // inside of Method2 ok, inside Method1 is a compiler error  
nameof(Stuff) = "Stuff"  
nameof(T) -> "T" // works inside of method but not in attributes on the method  
nameof(f) -> "f"  
nameof(f<T>) -> syntax error  
nameof(f<>) -> syntax error  
nameof(Method2()) -> error "This expression does not have a name"  
```  
  
## <a name="remarks"></a>Примечания  
 Аргументом для `nameof` должно быть простое имя, полное имя, доступ к членам, базовый доступ с заданным членом или доступ к this с указанным членом.  Выражение аргумента идентифицирует определение кода, но никогда не вычисляется.  
  
 Так как аргумент должен быть синтаксическим выражением, существует несколько запрещенных элементов, которые не следует перечислять.  Ниже приведены те элементы, которые могут приводить к ошибкам: предопределенные типы (например, `int` или `void`), типы, допускающие значение NULL (`Point?`), типы массивов (`Customer[,]`), типы указателей (`Buffer*`), полный псевдоним (`A::B`) и несвязанные универсальные типы (`Dictionary<,>`), символы предварительной обработки (`DEBUG`) и метки (`loop:`).  
  
 Если необходимо получить полное имя, можно использовать выражение `typeof` вместе с `nameof`.  Пример:
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 К сожалению, `typeof` не является константным выражением, как `nameof`, поэтому использовать `typeof` в сочетании с `nameof` в тех же местах, что и `nameof`, нельзя.  Например, следующий код приведет к ошибке компиляции CS0182:
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 В примерах показано, что можно использовать имя типа и получать доступ к имени метода экземпляра.  Не нужно иметь экземпляр типа, как это требуется в вычисленных выражениях.  Применение имени типа может оказаться очень удобным в некоторых ситуациях. Так как вы просто ссылаетесь на имя и не используете данные экземпляра, то не нужно придумывать переменную экземпляра или выражение.  
  
 В выражениях атрибутов в классе можно ссылаться на члены класса.  
  
 Сведения о сигнатурах, например "`Method1 (str, str)`", получить невозможно.  Чтобы это сделать, можно использовать выражение (`Expression e = () => A.B.Method1("s1", "s2")`) и извлечь MemberInfo из результирующего дерева выражения.  
  
## <a name="language-specifications"></a>Спецификации языков  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 

