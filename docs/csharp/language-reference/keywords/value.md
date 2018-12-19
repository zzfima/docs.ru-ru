---
title: value. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f0b9e2927eb288a27f926a740a967742b8cdaa9e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236470"
---
# <a name="value-c-reference"></a><span data-ttu-id="0a0ea-102">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0a0ea-102">value (C# Reference)</span></span>
<span data-ttu-id="0a0ea-103">Контекстное ключевое слово `value` используется в методе доступа set в обычных объявлениях свойств.</span><span class="sxs-lookup"><span data-stu-id="0a0ea-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="0a0ea-104">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="0a0ea-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="0a0ea-105">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.</span><span class="sxs-lookup"><span data-stu-id="0a0ea-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="0a0ea-106">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="0a0ea-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="0a0ea-107">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="0a0ea-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="0a0ea-108">Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="0a0ea-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0a0ea-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0a0ea-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a0ea-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0a0ea-110">See Also</span></span>

- [<span data-ttu-id="0a0ea-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0a0ea-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0a0ea-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0a0ea-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0a0ea-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0a0ea-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
