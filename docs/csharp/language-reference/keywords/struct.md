---
title: "struct (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- struct_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 23
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
ms.openlocfilehash: 309e68a57e1ee869850d960ffaac6cf35eb6e260
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="struct-c-reference"></a><span data-ttu-id="8ace0-102">struct (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8ace0-102">struct (C# Reference)</span></span>
<span data-ttu-id="8ace0-103">Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="8ace0-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="8ace0-104">В следующем примере показано простое объявление структуры:</span><span class="sxs-lookup"><span data-stu-id="8ace0-104">The following example shows a simple struct declaration:</span></span>  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ace0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ace0-105">Remarks</span></span>  
 <span data-ttu-id="8ace0-106">Структуры также могут содержать [конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md), [константы](../../../csharp/programming-guide/classes-and-structs/constants.md), [поля](../../../csharp/programming-guide/classes-and-structs/fields.md), [методы](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [индексаторы](../../../csharp/programming-guide/indexers/index.md), [операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [события](../../../csharp/programming-guide/events/index.md) и [вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.</span><span class="sxs-lookup"><span data-stu-id="8ace0-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="8ace0-107">Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="8ace0-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="8ace0-108">Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры.</span><span class="sxs-lookup"><span data-stu-id="8ace0-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="8ace0-109">По этой причине члены структуры не могут объявляться как `protected`.</span><span class="sxs-lookup"><span data-stu-id="8ace0-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="8ace0-110">Дополнительные сведения см. в разделе [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="8ace0-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8ace0-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ace0-111">Examples</span></span>  
 <span data-ttu-id="8ace0-112">Примеры и дополнительные сведения см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="8ace0-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8ace0-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8ace0-113">C# Language Specification</span></span>  
 <span data-ttu-id="8ace0-114">Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="8ace0-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ace0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8ace0-115">See Also</span></span>  
 <span data-ttu-id="8ace0-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8ace0-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8ace0-118">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="8ace0-119">[Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-119">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="8ace0-120">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-120">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="8ace0-121">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="8ace0-122">[Типы значений](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-122">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="8ace0-123">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-123">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="8ace0-124">[interface](../../../csharp/language-reference/keywords/interface.md) </span><span class="sxs-lookup"><span data-stu-id="8ace0-124">[interface](../../../csharp/language-reference/keywords/interface.md) </span></span>  
 [<span data-ttu-id="8ace0-125">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="8ace0-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

