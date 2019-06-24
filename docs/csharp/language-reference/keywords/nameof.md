---
title: nameof. Справочник по C#
ms.custom: seodec18
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 349cbf4e918d97a5a2a5c1e873d7fa114be8e2db
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306624"
---
# <a name="nameof-c-reference"></a><span data-ttu-id="a5922-102">nameof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a5922-102">nameof (C# Reference)</span></span>

<span data-ttu-id="a5922-103">Используется для получения простого (неполного) строкового имени переменной, типа или члена.</span><span class="sxs-lookup"><span data-stu-id="a5922-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>

<span data-ttu-id="a5922-104">При сообщении об ошибках в коде, подключении к ссылкам "модель — представление — контроллер" (MVC), запуске при событиях изменения свойств и т. д. часто требуется записать строковое имя метода.</span><span class="sxs-lookup"><span data-stu-id="a5922-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="a5922-105">`nameof` позволяет поддерживать код допустимым при переименовании определений.</span><span class="sxs-lookup"><span data-stu-id="a5922-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="a5922-106">Раньше приходилось использовать строковые литералы для ссылки на определения, что значительно усложняло работу при переименовании элементов кода, так как инструменты не могут проверять такие строковые литералы.</span><span class="sxs-lookup"><span data-stu-id="a5922-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>

<span data-ttu-id="a5922-107">Выражение `nameof` имеет следующую форму:</span><span class="sxs-lookup"><span data-stu-id="a5922-107">A `nameof` expression has this form:</span></span>

```csharp
if (x == null) throw new ArgumentNullException(nameof(x));
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"
```

## <a name="key-use-cases"></a><span data-ttu-id="a5922-108">Основные варианты использования</span><span class="sxs-lookup"><span data-stu-id="a5922-108">Key Use Cases</span></span>

<span data-ttu-id="a5922-109">В следующих примерах показаны основные варианты использования для `nameof`.</span><span class="sxs-lookup"><span data-stu-id="a5922-109">These examples show the key use cases for `nameof`.</span></span>

<span data-ttu-id="a5922-110">Проверка параметров:</span><span class="sxs-lookup"><span data-stu-id="a5922-110">Validate parameters:</span></span>

 ```csharp
void f(string s) {
    if (s == null) throw new ArgumentNullException(nameof(s));
}
```

<span data-ttu-id="a5922-111">Ссылки на действия MVC:</span><span class="sxs-lookup"><span data-stu-id="a5922-111">MVC Action links:</span></span>

```html
<%= Html.ActionLink("Sign up",
             @typeof(UserController),
             @nameof(UserController.SignUp))
%>
```

<span data-ttu-id="a5922-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="a5922-112">INotifyPropertyChanged:</span></span>

```csharp
int p {
    get { return this.p; }
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too
}
```

<span data-ttu-id="a5922-113">Свойство зависимости XAML:</span><span class="sxs-lookup"><span data-stu-id="a5922-113">XAML dependency property:</span></span>

```csharp
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));
```

<span data-ttu-id="a5922-114">Ведение журнала:</span><span class="sxs-lookup"><span data-stu-id="a5922-114">Logging:</span></span>

```csharp
void f(int i) {
    Log(nameof(f), "method entry");
}
```

<span data-ttu-id="a5922-115">Атрибуты:</span><span class="sxs-lookup"><span data-stu-id="a5922-115">Attributes:</span></span>

```csharp
[DebuggerDisplay("={" + nameof(GetString) + "()}")]
class C {
    string GetString() { }
}
```

## <a name="examples"></a><span data-ttu-id="a5922-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="a5922-116">Examples</span></span>

<span data-ttu-id="a5922-117">Некоторые примеры на C#:</span><span class="sxs-lookup"><span data-stu-id="a5922-117">Some C# examples:</span></span>

```csharp
using Stuff = Some.Cool.Functionality
class C {
    static int Method1 (string x, int y) {}
    static int Method1 (string x, string y) {}
    int Method2 (int z) {}
    string f<T>() => nameof(T);
}

var c = new C()

class Test {
    static void Main (string[] args) {
        Console.WriteLine(nameof(C)); // -> "C"
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]
        Console.WriteLine(nameof(f)); // -> "f"
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]
        // Console.WriteLine(nameof(f<>)); -> [syntax error]
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]
    }
}
```

## <a name="remarks"></a><span data-ttu-id="a5922-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5922-118">Remarks</span></span>

<span data-ttu-id="a5922-119">Аргументом для `nameof` должно быть простое имя, полное имя, доступ к членам, базовый доступ с заданным членом или доступ к this с указанным членом.</span><span class="sxs-lookup"><span data-stu-id="a5922-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="a5922-120">Выражение аргумента идентифицирует определение кода, но никогда не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="a5922-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>

<span data-ttu-id="a5922-121">Так как аргумент должен быть синтаксическим выражением, существует несколько запрещенных элементов, которые не следует перечислять.</span><span class="sxs-lookup"><span data-stu-id="a5922-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="a5922-122">Ниже приведены те элементы, которые могут приводить к ошибкам: предопределенные типы (например, `int` или `void`), типы, допускающие значение NULL (`Point?`), типы массивов (`Customer[,]`), типы указателей (`Buffer*`), полный псевдоним (`A::B`) и несвязанные универсальные типы (`Dictionary<,>`), символы предварительной обработки (`DEBUG`) и метки (`loop:`).</span><span class="sxs-lookup"><span data-stu-id="a5922-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>

<span data-ttu-id="a5922-123">Если необходимо получить полное имя, можно использовать выражение `typeof` вместе с `nameof`.</span><span class="sxs-lookup"><span data-stu-id="a5922-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="a5922-124">Например:</span><span class="sxs-lookup"><span data-stu-id="a5922-124">For example:</span></span>

```csharp
class C {
    void f(int i) {
        Log($"{typeof(C)}.{nameof(f)}", "method entry");
    }
}
```

<span data-ttu-id="a5922-125">К сожалению, `typeof` не является константным выражением, как `nameof`, поэтому использовать `typeof` в сочетании с `nameof` в тех же местах, что и `nameof`, нельзя.</span><span class="sxs-lookup"><span data-stu-id="a5922-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="a5922-126">Например, следующий код приведет к ошибке компиляции CS0182:</span><span class="sxs-lookup"><span data-stu-id="a5922-126">For example, the following would cause a CS0182 compile error:</span></span>

```csharp
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]
class C {
    string GetString() { }
}
```

<span data-ttu-id="a5922-127">В примерах показано, что можно использовать имя типа и получать доступ к имени метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a5922-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="a5922-128">Не нужно иметь экземпляр типа, как это требуется в вычисленных выражениях.</span><span class="sxs-lookup"><span data-stu-id="a5922-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="a5922-129">Применение имени типа может оказаться очень удобным в некоторых ситуациях. Так как вы просто ссылаетесь на имя и не используете данные экземпляра, то не нужно придумывать переменную экземпляра или выражение.</span><span class="sxs-lookup"><span data-stu-id="a5922-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>

<span data-ttu-id="a5922-130">В выражениях атрибутов в классе можно ссылаться на члены класса.</span><span class="sxs-lookup"><span data-stu-id="a5922-130">You can reference the members of a class in attribute expressions on the class.</span></span>

<span data-ttu-id="a5922-131">Сведения о сигнатурах, например "`Method1 (str, str)`", получить невозможно.</span><span class="sxs-lookup"><span data-stu-id="a5922-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="a5922-132">Чтобы это сделать, можно использовать выражение (`Expression e = () => A.B.Method1("s1", "s2")`) и извлечь MemberInfo из результирующего дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="a5922-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="a5922-133">Спецификации языков</span><span class="sxs-lookup"><span data-stu-id="a5922-133">Language Specifications</span></span>

<span data-ttu-id="a5922-134">Дополнительные сведения см. в разделе [Выражения Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5922-134">For more information, see [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="a5922-135">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="a5922-135">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5922-136">См. также</span><span class="sxs-lookup"><span data-stu-id="a5922-136">See also</span></span>

- [<span data-ttu-id="a5922-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a5922-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="a5922-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a5922-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a5922-139">typeof</span><span class="sxs-lookup"><span data-stu-id="a5922-139">typeof</span></span>](../operators/type-testing-and-conversion-operators.md#typeof-operator)
