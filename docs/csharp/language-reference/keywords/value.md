---
title: "value (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2501bc8964ed76534dba6c7cc519e095c57cb898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="value-c-reference"></a><span data-ttu-id="6fbb8-102">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6fbb8-102">value (C# Reference)</span></span>
<span data-ttu-id="6fbb8-103">Контекстное ключевое слово `value` используется в методе доступа set в обычных объявлениях свойств.</span><span class="sxs-lookup"><span data-stu-id="6fbb8-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="6fbb8-104">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="6fbb8-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="6fbb8-105">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.</span><span class="sxs-lookup"><span data-stu-id="6fbb8-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="6fbb8-106">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="6fbb8-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="6fbb8-107">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="6fbb8-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="6fbb8-108">Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="6fbb8-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6fbb8-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6fbb8-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6fbb8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6fbb8-110">See Also</span></span>  
 [<span data-ttu-id="6fbb8-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6fbb8-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6fbb8-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6fbb8-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6fbb8-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6fbb8-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
