---
title: "value (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
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
ms.openlocfilehash: 012cf622091687996fec477a8b5b821b190bbc29
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="value-c-reference"></a><span data-ttu-id="b71e3-102">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b71e3-102">value (C# Reference)</span></span>
<span data-ttu-id="b71e3-103">Контекстное ключевое слово `value` используется в методе доступа set в обычных объявлениях свойств.</span><span class="sxs-lookup"><span data-stu-id="b71e3-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="b71e3-104">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="b71e3-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="b71e3-105">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.</span><span class="sxs-lookup"><span data-stu-id="b71e3-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="b71e3-106">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="b71e3-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="b71e3-107">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="b71e3-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 <span data-ttu-id="b71e3-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b71e3-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span></span>  
  
 <span data-ttu-id="b71e3-109">Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="b71e3-109">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b71e3-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b71e3-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b71e3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b71e3-111">See Also</span></span>  
 <span data-ttu-id="b71e3-112">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b71e3-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b71e3-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b71e3-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b71e3-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b71e3-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

