---
title: "struct (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e8a848d5543291ef335e72cb7806158827e865dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="struct-c-reference"></a><span data-ttu-id="a3c54-102">struct (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a3c54-102">struct (C# Reference)</span></span>
<span data-ttu-id="a3c54-103">Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="a3c54-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="a3c54-104">В следующем примере показано простое объявление структуры:</span><span class="sxs-lookup"><span data-stu-id="a3c54-104">The following example shows a simple struct declaration:</span></span>  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="a3c54-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="a3c54-105">Remarks</span></span>  
 <span data-ttu-id="a3c54-106">Структуры также могут содержать [конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md), [константы](../../../csharp/programming-guide/classes-and-structs/constants.md), [поля](../../../csharp/programming-guide/classes-and-structs/fields.md), [методы](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [индексаторы](../../../csharp/programming-guide/indexers/index.md), [операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [события](../../../csharp/programming-guide/events/index.md) и [вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.</span><span class="sxs-lookup"><span data-stu-id="a3c54-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="a3c54-107">Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="a3c54-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="a3c54-108">Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры.</span><span class="sxs-lookup"><span data-stu-id="a3c54-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="a3c54-109">По этой причине члены структуры не могут объявляться как `protected`.</span><span class="sxs-lookup"><span data-stu-id="a3c54-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="a3c54-110">Дополнительные сведения см. в разделе [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="a3c54-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a3c54-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="a3c54-111">Examples</span></span>  
 <span data-ttu-id="a3c54-112">Примеры и дополнительные сведения см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="a3c54-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a3c54-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a3c54-113">C# Language Specification</span></span>  
 <span data-ttu-id="a3c54-114">Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="a3c54-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c54-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a3c54-115">See Also</span></span>  
 [<span data-ttu-id="a3c54-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a3c54-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a3c54-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a3c54-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a3c54-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a3c54-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a3c54-119">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a3c54-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="a3c54-120">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="a3c54-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="a3c54-121">Типы</span><span class="sxs-lookup"><span data-stu-id="a3c54-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="a3c54-122">Типы значений</span><span class="sxs-lookup"><span data-stu-id="a3c54-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="a3c54-123">class</span><span class="sxs-lookup"><span data-stu-id="a3c54-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="a3c54-124">interface</span><span class="sxs-lookup"><span data-stu-id="a3c54-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
 [<span data-ttu-id="a3c54-125">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="a3c54-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
