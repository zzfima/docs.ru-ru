---
title: Модификатор static. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: b288e57d9241e294a0fa18edafe72eec675327a7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633190"
---
# <a name="static-c-reference"></a><span data-ttu-id="db923-102">static (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="db923-102">static (C# Reference)</span></span>

<span data-ttu-id="db923-103">Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту.</span><span class="sxs-lookup"><span data-stu-id="db923-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="db923-104">Модификатор `static` можно использовать с классами, полями, методами, свойствами, операторами, событиями и конструкторами, но нельзя — с индексаторами, методами завершения или типами, отличными от классов.</span><span class="sxs-lookup"><span data-stu-id="db923-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="db923-105">Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="db923-105">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="db923-106">Пример</span><span class="sxs-lookup"><span data-stu-id="db923-106">Example</span></span>

<span data-ttu-id="db923-107">Следующий класс объявляется как `static` и содержит только методы `static`:</span><span class="sxs-lookup"><span data-stu-id="db923-107">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="db923-108">Объявление константы или типа неявно является статическим членом.</span><span class="sxs-lookup"><span data-stu-id="db923-108">A constant or type declaration is implicitly a static member.</span></span>

<span data-ttu-id="db923-109">На статический член нельзя ссылаться через экземпляр,</span><span class="sxs-lookup"><span data-stu-id="db923-109">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="db923-110">а можно только через имя типа.</span><span class="sxs-lookup"><span data-stu-id="db923-110">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="db923-111">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="db923-111">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="db923-112">Чтобы обратиться к статическому члену `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` (если только член не доступен из той же области действия):</span><span class="sxs-lookup"><span data-stu-id="db923-112">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="db923-113">Так как экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому статическому полю соответствует только одна копия.</span><span class="sxs-lookup"><span data-stu-id="db923-113">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>

<span data-ttu-id="db923-114">Невозможно использовать [this](this.md) для ссылки на статические методы или методы доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="db923-114">It is not possible to use [this](this.md) to reference static methods or property accessors.</span></span>

<span data-ttu-id="db923-115">Если к классу применяется ключевое слово `static`, все члены этого класса должны быть статическими.</span><span class="sxs-lookup"><span data-stu-id="db923-115">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>

<span data-ttu-id="db923-116">Классы и статические классы могут иметь статические конструкторы.</span><span class="sxs-lookup"><span data-stu-id="db923-116">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="db923-117">Статические конструкторы вызываются на определенном этапе между запуском программы и созданием экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="db923-117">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="db923-118">Ключевое слово `static` имеет более ограниченное применение по сравнению с C++.</span><span class="sxs-lookup"><span data-stu-id="db923-118">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="db923-119">Сведения о сравнении с ключевым словом С++ см. в статье [Классы хранения (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="db923-119">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="db923-120">В качестве демонстрации статических членов рассмотрим класс, представляющий сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="db923-120">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="db923-121">Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа.</span><span class="sxs-lookup"><span data-stu-id="db923-121">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="db923-122">И метод, и поле не принадлежат никакому экземпляру сотрудника.</span><span class="sxs-lookup"><span data-stu-id="db923-122">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="db923-123">Они принадлежат классу компании.</span><span class="sxs-lookup"><span data-stu-id="db923-123">Instead they belong to the company class.</span></span> <span data-ttu-id="db923-124">В связи с этим они должны объявляться как статические члены класса.</span><span class="sxs-lookup"><span data-stu-id="db923-124">Therefore, they should be declared as static members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="db923-125">Пример</span><span class="sxs-lookup"><span data-stu-id="db923-125">Example</span></span>

<span data-ttu-id="db923-126">В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и новом числе сотрудников.</span><span class="sxs-lookup"><span data-stu-id="db923-126">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="db923-127">Для простоты эта программа считывает текущее число сотрудников с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="db923-127">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="db923-128">В реальном приложении эта информация должна считываться из файла.</span><span class="sxs-lookup"><span data-stu-id="db923-128">In a real application, this information should be read from a file.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="db923-129">Пример</span><span class="sxs-lookup"><span data-stu-id="db923-129">Example</span></span>

<span data-ttu-id="db923-130">Этот пример показывает, что несмотря на то, что вы можете инициализировать статическое поле посредством другого, еще не объявленного статического поля, результаты не будут определены до тех пор, пока статическому полю не будет явно присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="db923-130">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="db923-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="db923-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="db923-132">См. также</span><span class="sxs-lookup"><span data-stu-id="db923-132">See also</span></span>

- [<span data-ttu-id="db923-133">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="db923-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="db923-134">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="db923-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="db923-135">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="db923-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="db923-136">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="db923-136">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="db923-137">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="db923-137">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
