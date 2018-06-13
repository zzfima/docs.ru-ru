---
title: value (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: c8f808540385552f6222566f23251f6cbd6e86df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265276"
---
# <a name="value-c-reference"></a><span data-ttu-id="d15b5-102">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d15b5-102">value (C# Reference)</span></span>
<span data-ttu-id="d15b5-103">Контекстное ключевое слово `value` используется в методе доступа set в обычных объявлениях свойств.</span><span class="sxs-lookup"><span data-stu-id="d15b5-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="d15b5-104">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="d15b5-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="d15b5-105">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.</span><span class="sxs-lookup"><span data-stu-id="d15b5-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="d15b5-106">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="d15b5-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="d15b5-107">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="d15b5-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="d15b5-108">Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="d15b5-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d15b5-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d15b5-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d15b5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d15b5-110">See Also</span></span>  
 [<span data-ttu-id="d15b5-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d15b5-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d15b5-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d15b5-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d15b5-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d15b5-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
