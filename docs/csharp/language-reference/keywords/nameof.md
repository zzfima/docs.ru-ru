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
# <a name="nameof-c-reference"></a><span data-ttu-id="9e474-102">nameof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9e474-102">nameof (C# Reference)</span></span>

<span data-ttu-id="9e474-103">Используется для получения простого (неполного) строкового имени переменной, типа или члена.</span><span class="sxs-lookup"><span data-stu-id="9e474-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>  

<span data-ttu-id="9e474-104">При сообщении об ошибках в коде, подключении к ссылкам "модель — представление — контроллер" (MVC), запуске при событиях изменения свойств и т. д. часто требуется записать строковое имя метода.</span><span class="sxs-lookup"><span data-stu-id="9e474-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="9e474-105">`nameof` позволяет поддерживать код допустимым при переименовании определений.</span><span class="sxs-lookup"><span data-stu-id="9e474-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="9e474-106">Раньше приходилось использовать строковые литералы для ссылки на определения, что значительно усложняло работу при переименовании элементов кода, так как инструменты не могут проверять такие строковые литералы.</span><span class="sxs-lookup"><span data-stu-id="9e474-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>  
  
 <span data-ttu-id="9e474-107">Выражение `nameof` имеет следующую форму:</span><span class="sxs-lookup"><span data-stu-id="9e474-107">A `nameof` expression has this form:</span></span>  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a><span data-ttu-id="9e474-108">Основные варианты использования</span><span class="sxs-lookup"><span data-stu-id="9e474-108">Key Use Cases</span></span>  
 <span data-ttu-id="9e474-109">В следующих примерах показаны основные варианты использования для `nameof`.</span><span class="sxs-lookup"><span data-stu-id="9e474-109">These examples show the key use cases for `nameof`.</span></span>  
  
 <span data-ttu-id="9e474-110">Проверка параметров:</span><span class="sxs-lookup"><span data-stu-id="9e474-110">Validate parameters:</span></span>  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 <span data-ttu-id="9e474-111">Ссылки на действия MVC:</span><span class="sxs-lookup"><span data-stu-id="9e474-111">MVC Action links:</span></span>  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 <span data-ttu-id="9e474-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="9e474-112">INotifyPropertyChanged:</span></span>  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 <span data-ttu-id="9e474-113">Свойство зависимости XAML:</span><span class="sxs-lookup"><span data-stu-id="9e474-113">XAML dependency property:</span></span>  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 <span data-ttu-id="9e474-114">Ведение журнала:</span><span class="sxs-lookup"><span data-stu-id="9e474-114">Logging:</span></span>  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 <span data-ttu-id="9e474-115">Атрибуты:</span><span class="sxs-lookup"><span data-stu-id="9e474-115">Attributes:</span></span>  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a><span data-ttu-id="9e474-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="9e474-116">Examples</span></span>  
 <span data-ttu-id="9e474-117">Некоторые примеры на C#:</span><span class="sxs-lookup"><span data-stu-id="9e474-117">Some C# examples:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="9e474-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e474-118">Remarks</span></span>  
 <span data-ttu-id="9e474-119">Аргументом для `nameof` должно быть простое имя, полное имя, доступ к членам, базовый доступ с заданным членом или доступ к this с указанным членом.</span><span class="sxs-lookup"><span data-stu-id="9e474-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="9e474-120">Выражение аргумента идентифицирует определение кода, но никогда не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="9e474-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>  
  
 <span data-ttu-id="9e474-121">Так как аргумент должен быть синтаксическим выражением, существует несколько запрещенных элементов, которые не следует перечислять.</span><span class="sxs-lookup"><span data-stu-id="9e474-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="9e474-122">Ниже приведены те элементы, которые могут приводить к ошибкам: предопределенные типы (например, `int` или `void`), типы, допускающие значение NULL (`Point?`), типы массивов (`Customer[,]`), типы указателей (`Buffer*`), полный псевдоним (`A::B`) и несвязанные универсальные типы (`Dictionary<,>`), символы предварительной обработки (`DEBUG`) и метки (`loop:`).</span><span class="sxs-lookup"><span data-stu-id="9e474-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>  
  
 <span data-ttu-id="9e474-123">Если необходимо получить полное имя, можно использовать выражение `typeof` вместе с `nameof`.</span><span class="sxs-lookup"><span data-stu-id="9e474-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="9e474-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="9e474-124">For example:</span></span>
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 <span data-ttu-id="9e474-125">К сожалению, `typeof` не является константным выражением, как `nameof`, поэтому использовать `typeof` в сочетании с `nameof` в тех же местах, что и `nameof`, нельзя.</span><span class="sxs-lookup"><span data-stu-id="9e474-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="9e474-126">Например, следующий код приведет к ошибке компиляции CS0182:</span><span class="sxs-lookup"><span data-stu-id="9e474-126">For example, the following would cause a CS0182 compile error:</span></span>
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 <span data-ttu-id="9e474-127">В примерах показано, что можно использовать имя типа и получать доступ к имени метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9e474-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="9e474-128">Не нужно иметь экземпляр типа, как это требуется в вычисленных выражениях.</span><span class="sxs-lookup"><span data-stu-id="9e474-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="9e474-129">Применение имени типа может оказаться очень удобным в некоторых ситуациях. Так как вы просто ссылаетесь на имя и не используете данные экземпляра, то не нужно придумывать переменную экземпляра или выражение.</span><span class="sxs-lookup"><span data-stu-id="9e474-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>  
  
 <span data-ttu-id="9e474-130">В выражениях атрибутов в классе можно ссылаться на члены класса.</span><span class="sxs-lookup"><span data-stu-id="9e474-130">You can reference the members of a class in attribute expressions on the class.</span></span>  
  
 <span data-ttu-id="9e474-131">Сведения о сигнатурах, например "`Method1 (str, str)`", получить невозможно.</span><span class="sxs-lookup"><span data-stu-id="9e474-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="9e474-132">Чтобы это сделать, можно использовать выражение (`Expression e = () => A.B.Method1("s1", "s2")`) и извлечь MemberInfo из результирующего дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="9e474-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="9e474-133">Спецификации языков</span><span class="sxs-lookup"><span data-stu-id="9e474-133">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e474-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9e474-134">See Also</span></span>  
 <span data-ttu-id="9e474-135">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e474-135">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9e474-136">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e474-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9e474-137">typeof</span><span class="sxs-lookup"><span data-stu-id="9e474-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)   
 

