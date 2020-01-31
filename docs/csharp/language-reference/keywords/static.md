---
title: Модификатор static. Справочник по C#
ms.date: 01/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: e7671e9db488a7b50f4ed736864d6fa8d95eef1a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744661"
---
# <a name="static-c-reference"></a><span data-ttu-id="5f14b-102">static (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5f14b-102">static (C# Reference)</span></span>

<span data-ttu-id="5f14b-103">Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту.</span><span class="sxs-lookup"><span data-stu-id="5f14b-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="5f14b-104">Модификатор `static` можно использовать для объявления классов `static`.</span><span class="sxs-lookup"><span data-stu-id="5f14b-104">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="5f14b-105">В классах, интерфейсах и структурах вы можете добавить модификатор `static` к полям, методам, свойствам, операторам, событиям и конструкторам.</span><span class="sxs-lookup"><span data-stu-id="5f14b-105">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="5f14b-106">Модификатор `static` запрещено использовать с индексаторами или методами завершения.</span><span class="sxs-lookup"><span data-stu-id="5f14b-106">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="5f14b-107">Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="5f14b-107">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="5f14b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5f14b-108">Example</span></span>

<span data-ttu-id="5f14b-109">Следующий класс объявляется как `static` и содержит только методы `static`:</span><span class="sxs-lookup"><span data-stu-id="5f14b-109">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="5f14b-110">Объявление константы или типа неявно является членом `static`.</span><span class="sxs-lookup"><span data-stu-id="5f14b-110">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="5f14b-111">На член `static` невозможно ссылаться через экземпляр,</span><span class="sxs-lookup"><span data-stu-id="5f14b-111">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="5f14b-112">а можно только через имя типа.</span><span class="sxs-lookup"><span data-stu-id="5f14b-112">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="5f14b-113">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="5f14b-113">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="5f14b-114">Чтобы обратиться к члену `static` `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` (если только член не доступен из той же области действия).</span><span class="sxs-lookup"><span data-stu-id="5f14b-114">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="5f14b-115">Так как экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому полю `static` соответствует только одна копия.</span><span class="sxs-lookup"><span data-stu-id="5f14b-115">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="5f14b-116">Невозможно использовать [`this`](this.md) для ссылки на методы `static` или методы доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="5f14b-116">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="5f14b-117">Если к классу применяется ключевое слово `static`, все члены этого класса должны быть `static`.</span><span class="sxs-lookup"><span data-stu-id="5f14b-117">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="5f14b-118">Классы, интерфейсы и классы `static` могут иметь конструкторы `static`.</span><span class="sxs-lookup"><span data-stu-id="5f14b-118">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="5f14b-119">Конструктор `static` вызывается на определенном этапе между запуском программы и созданием экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="5f14b-119">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="5f14b-120">Ключевое слово `static` имеет более ограниченное применение по сравнению с C++.</span><span class="sxs-lookup"><span data-stu-id="5f14b-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="5f14b-121">Сведения о сравнении с ключевым словом С++ см. в статье [Классы хранения (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="5f14b-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="5f14b-122">В качестве демонстрации членов `static` рассмотрим класс, представляющий сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="5f14b-122">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="5f14b-123">Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа.</span><span class="sxs-lookup"><span data-stu-id="5f14b-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="5f14b-124">И метод, и поле не принадлежат никакому экземпляру сотрудника.</span><span class="sxs-lookup"><span data-stu-id="5f14b-124">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="5f14b-125">Они принадлежат всему классу сотрудников.</span><span class="sxs-lookup"><span data-stu-id="5f14b-125">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="5f14b-126">В связи с этим они должны объявляться как члены `static` класса.</span><span class="sxs-lookup"><span data-stu-id="5f14b-126">They should be declared as `static` members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="5f14b-127">Пример</span><span class="sxs-lookup"><span data-stu-id="5f14b-127">Example</span></span>

<span data-ttu-id="5f14b-128">В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и новом числе сотрудников.</span><span class="sxs-lookup"><span data-stu-id="5f14b-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="5f14b-129">Эта программа считывает текущее число сотрудников с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="5f14b-129">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="5f14b-130">Пример</span><span class="sxs-lookup"><span data-stu-id="5f14b-130">Example</span></span>

<span data-ttu-id="5f14b-131">В этом примере показано, как можно инициализировать поле `static`, используя другое поле `static`, которое еще не объявлено.</span><span class="sxs-lookup"><span data-stu-id="5f14b-131">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="5f14b-132">Результаты будут неопределенными до тех пор, пока вы явно не присвоите значение полю `static`.</span><span class="sxs-lookup"><span data-stu-id="5f14b-132">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="5f14b-133">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5f14b-133">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5f14b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5f14b-134">See also</span></span>

- [<span data-ttu-id="5f14b-135">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5f14b-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5f14b-136">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5f14b-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5f14b-137">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="5f14b-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5f14b-138">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="5f14b-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5f14b-139">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="5f14b-139">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
