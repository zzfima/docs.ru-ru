---
title: "const (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
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
ms.openlocfilehash: b8f6d567deed513ff5693fe39bd21c8607677402
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="const-c-reference"></a><span data-ttu-id="18ef2-102">const (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="18ef2-102">const (C# Reference)</span></span>
<span data-ttu-id="18ef2-103">Для объявления константного поля или константной локальной используется ключевое слово `const`.</span><span class="sxs-lookup"><span data-stu-id="18ef2-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="18ef2-104">Константные поля и локальные не являются переменными и не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="18ef2-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="18ef2-105">Константы могут быть числами, логическими значениями, строками или нулевыми ссылками.</span><span class="sxs-lookup"><span data-stu-id="18ef2-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="18ef2-106">Не создавайте константу для предоставления сведений, которые могут измениться в любое время.</span><span class="sxs-lookup"><span data-stu-id="18ef2-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="18ef2-107">Например, не используйте константное поле для хранения цены услуги, номера версии продукта или торгового названия компании.</span><span class="sxs-lookup"><span data-stu-id="18ef2-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="18ef2-108">Эти значения могут со временем измениться, а поскольку константы распространяются компиляторами, для отражения изменений потребуется повторная компиляция остальных кодов, скомпилированных с использованием ваших библиотек.</span><span class="sxs-lookup"><span data-stu-id="18ef2-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="18ef2-109">См. также описание ключевого слова [readonly](../../../csharp/language-reference/keywords/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="18ef2-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="18ef2-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="18ef2-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="18ef2-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="18ef2-111">Remarks</span></span>  
 <span data-ttu-id="18ef2-112">Тип объявления константы указывает на тип членов, которые вводятся объявлением.</span><span class="sxs-lookup"><span data-stu-id="18ef2-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="18ef2-113">Инициализатор константной локальной или константного поля должен быть выражением константы, поддерживающим явное преобразование в конечный тип.</span><span class="sxs-lookup"><span data-stu-id="18ef2-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="18ef2-114">Выражение константы — это выражение, которое можно полностью оценить во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="18ef2-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="18ef2-115">Таким образом, единственно возможными значениями для констант типов ссылок являются `string` и нулевые ссылки.</span><span class="sxs-lookup"><span data-stu-id="18ef2-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="18ef2-116">Объявление константы может объявлять несколько констант, например:</span><span class="sxs-lookup"><span data-stu-id="18ef2-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="18ef2-117">Модификатор `static` в объявлении константы не допускается.</span><span class="sxs-lookup"><span data-stu-id="18ef2-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="18ef2-118">Константа может участвовать в выражении константы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="18ef2-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="18ef2-119">Ключевое слово [readonly](../../../csharp/language-reference/keywords/readonly.md) отличается от ключевого слова `const`.</span><span class="sxs-lookup"><span data-stu-id="18ef2-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="18ef2-120">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="18ef2-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="18ef2-121">Поле `readonly` может быть инициализировано при объявлении или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="18ef2-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="18ef2-122">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="18ef2-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="18ef2-123">Также, несмотря на то, что поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующей строке: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="18ef2-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ef2-124">Пример</span><span class="sxs-lookup"><span data-stu-id="18ef2-124">Example</span></span>  
 <span data-ttu-id="18ef2-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="18ef2-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ef2-126">Пример</span><span class="sxs-lookup"><span data-stu-id="18ef2-126">Example</span></span>  
 <span data-ttu-id="18ef2-127">В этом примере показан способ использования констант в качестве локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="18ef2-127">This example demonstrates how to use constants as local variables.</span></span>  
  
 <span data-ttu-id="18ef2-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="18ef2-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="18ef2-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="18ef2-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18ef2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="18ef2-130">See Also</span></span>  
 <span data-ttu-id="18ef2-131">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="18ef2-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="18ef2-132">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="18ef2-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="18ef2-133">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="18ef2-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="18ef2-134">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="18ef2-134">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="18ef2-135">readonly</span><span class="sxs-lookup"><span data-stu-id="18ef2-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)

