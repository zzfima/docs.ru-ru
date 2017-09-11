---
title: "Константы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
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
ms.openlocfilehash: 85273420e9e0dbf4b8f24568d97be127c85d5f42
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="a7ace-102">Константы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a7ace-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="a7ace-103">Константы — это постоянные значения, которые известны во время компиляции и не изменяются во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="a7ace-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="a7ace-104">Константы должны объявляться с модификатором [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="a7ace-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="a7ace-105">Только встроенные типы C# (за исключением <xref:System.Object?displayProperty=fullName>) можно объявлять как `const`.</span><span class="sxs-lookup"><span data-stu-id="a7ace-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=fullName>) may be declared as `const`.</span></span> <span data-ttu-id="a7ace-106">Список встроенных типов см. в [таблице встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="a7ace-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="a7ace-107">Пользовательские типы, включая классы, структуры и массивы, не могут объявляться как `const`.</span><span class="sxs-lookup"><span data-stu-id="a7ace-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="a7ace-108">Модификатор [readonly](../../../csharp/language-reference/keywords/readonly.md) позволяет создать класс, структуру или массив, которые инициализируются один раз (например, в конструкторе), и впоследствии изменить их нельзя.</span><span class="sxs-lookup"><span data-stu-id="a7ace-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="a7ace-109">C# не поддерживает методы, свойства или события `const`.</span><span class="sxs-lookup"><span data-stu-id="a7ace-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="a7ace-110">Тип перечисления позволяет определять именованные константы для целочисленных встроенных типов (например `int`, `uint`, `long` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a7ace-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="a7ace-111">Дополнительные сведения см. в разделе [Перечисление](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="a7ace-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="a7ace-112">Константы должны инициализироваться сразу после объявления.</span><span class="sxs-lookup"><span data-stu-id="a7ace-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="a7ace-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="a7ace-113">For example:</span></span>  
  
 <span data-ttu-id="a7ace-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a7ace-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span></span>  
  
 <span data-ttu-id="a7ace-115">В этом примере константа `months` всегда имеет значение 12, и его не может изменить даже сам класс.</span><span class="sxs-lookup"><span data-stu-id="a7ace-115">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="a7ace-116">На самом деле в случае, если компилятор встречает идентификатор константы в исходном коде C# (например, `months`), он подставляет значение литерала непосредственно в создаваемый им промежуточный язык (IL).</span><span class="sxs-lookup"><span data-stu-id="a7ace-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="a7ace-117">Поскольку с константой в среде выполнения не связан адрес ни одной переменной, поля `const` не могут передаваться по ссылке и отображаться в выражении как левостороннее значение.</span><span class="sxs-lookup"><span data-stu-id="a7ace-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7ace-118">Будьте внимательны, ссылаясь на постоянные значения, определенные в другом коде, например, в DLL.</span><span class="sxs-lookup"><span data-stu-id="a7ace-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="a7ace-119">Если в новой версии DLL для константы определяется новое значение, старое значение литерала хранится в вашей программе вплоть до повторной компиляции для новой версии.</span><span class="sxs-lookup"><span data-stu-id="a7ace-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="a7ace-120">Несколько констант одного типа можно объявить одновременно, например:</span><span class="sxs-lookup"><span data-stu-id="a7ace-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 <span data-ttu-id="a7ace-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a7ace-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span></span>  
  
 <span data-ttu-id="a7ace-122">Выражение, которое используется для инициализации константы, может ссылаться на другую константу, если не создает циклическую ссылку.</span><span class="sxs-lookup"><span data-stu-id="a7ace-122">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="a7ace-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="a7ace-123">For example:</span></span>  
  
 <span data-ttu-id="a7ace-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a7ace-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span></span>  
  
 <span data-ttu-id="a7ace-125">Константы могут иметь пометку [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="a7ace-125">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="a7ace-126">Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к константе.</span><span class="sxs-lookup"><span data-stu-id="a7ace-126">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="a7ace-127">Дополнительные сведения см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a7ace-127">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="a7ace-128">Доступ к константам осуществляется так, как если бы они были [статическими](../../../csharp/language-reference/keywords/static.md) полями, поскольку значение константы одинаково для всех экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="a7ace-128">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="a7ace-129">Для их объявления используйте ключевое слово `static`.</span><span class="sxs-lookup"><span data-stu-id="a7ace-129">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="a7ace-130">Выражения, которые не относятся к классу, определяющему константу, должны включать имя класса, период и имя константы для доступа к этой константе.</span><span class="sxs-lookup"><span data-stu-id="a7ace-130">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="a7ace-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="a7ace-131">For example:</span></span>  
  
 <span data-ttu-id="a7ace-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a7ace-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a7ace-133">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a7ace-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7ace-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a7ace-134">See Also</span></span>  
 <span data-ttu-id="a7ace-135">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7ace-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a7ace-136">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7ace-136">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="a7ace-137">[Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="a7ace-137">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="a7ace-138">[Типы](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7ace-138">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="a7ace-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="a7ace-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span></span>  
 [<span data-ttu-id="a7ace-140">Неизменность в C#, часть 1. Виды неизменности</span><span class="sxs-lookup"><span data-stu-id="a7ace-140">Immutability in C# Part One: Kinds of Immutability</span></span>](http://go.microsoft.com/fwlink/?LinkId=112379)

