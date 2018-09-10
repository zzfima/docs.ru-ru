---
title: struct (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 7931da2e5f5c493b54eb1f33a1d6f57b38592f6e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530196"
---
# <a name="struct-c-reference"></a><span data-ttu-id="28db9-102">struct (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="28db9-102">struct (C# Reference)</span></span>
<span data-ttu-id="28db9-103">Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="28db9-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="28db9-104">В следующем примере показано простое объявление структуры:</span><span class="sxs-lookup"><span data-stu-id="28db9-104">The following example shows a simple struct declaration:</span></span>  
  
```csharp  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="28db9-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="28db9-105">Remarks</span></span>  
 <span data-ttu-id="28db9-106">Структуры также могут содержать [конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md), [константы](../../../csharp/programming-guide/classes-and-structs/constants.md), [поля](../../../csharp/programming-guide/classes-and-structs/fields.md), [методы](../../../csharp/programming-guide/classes-and-structs/methods.md), [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [индексаторы](../../../csharp/programming-guide/indexers/index.md), [операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [события](../../../csharp/programming-guide/events/index.md) и [вложенные типы](../../../csharp/programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.</span><span class="sxs-lookup"><span data-stu-id="28db9-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="28db9-107">Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="28db9-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="28db9-108">Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры.</span><span class="sxs-lookup"><span data-stu-id="28db9-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="28db9-109">По этой причине члены структуры не могут объявляться как `protected`.</span><span class="sxs-lookup"><span data-stu-id="28db9-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="28db9-110">Дополнительные сведения см. в разделе [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="28db9-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="28db9-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="28db9-111">Examples</span></span>  
 <span data-ttu-id="28db9-112">Примеры и дополнительные сведения см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="28db9-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="28db9-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="28db9-113">C# Language Specification</span></span>  
 <span data-ttu-id="28db9-114">Примеры см. в разделе [Использование структур](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="28db9-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28db9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="28db9-115">See Also</span></span>

- [<span data-ttu-id="28db9-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="28db9-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="28db9-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="28db9-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="28db9-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="28db9-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="28db9-119">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="28db9-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
- [<span data-ttu-id="28db9-120">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="28db9-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="28db9-121">Типы</span><span class="sxs-lookup"><span data-stu-id="28db9-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="28db9-122">Типы значений</span><span class="sxs-lookup"><span data-stu-id="28db9-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="28db9-123">class</span><span class="sxs-lookup"><span data-stu-id="28db9-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
- [<span data-ttu-id="28db9-124">interface</span><span class="sxs-lookup"><span data-stu-id="28db9-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
- [<span data-ttu-id="28db9-125">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="28db9-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
