---
title: struct. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 77d5c83dd4c81b96bc62ace6e609db8bc411dc41
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093166"
---
# <a name="struct-c-reference"></a><span data-ttu-id="d827d-102">struct (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d827d-102">struct (C# Reference)</span></span>

<span data-ttu-id="d827d-103">Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="d827d-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="d827d-104">В следующем примере показано простое объявление структуры:</span><span class="sxs-lookup"><span data-stu-id="d827d-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="d827d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d827d-105">Remarks</span></span>

<span data-ttu-id="d827d-106">Структуры также могут содержать [конструкторы](../../programming-guide/classes-and-structs/constructors.md), [константы](../../programming-guide/classes-and-structs/constants.md), [поля](../../programming-guide/classes-and-structs/fields.md), [методы](../../programming-guide/classes-and-structs/methods.md), [свойства](../../programming-guide/classes-and-structs/properties.md), [индексаторы](../../programming-guide/indexers/index.md), [операторы](../operators/index.md), [события](../../programming-guide/events/index.md) и [вложенные типы](../../programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.</span><span class="sxs-lookup"><span data-stu-id="d827d-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="d827d-107">Примеры см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="d827d-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="d827d-108">Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры.</span><span class="sxs-lookup"><span data-stu-id="d827d-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="d827d-109">По этой причине члены структуры не могут объявляться как `protected`.</span><span class="sxs-lookup"><span data-stu-id="d827d-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="d827d-110">Дополнительные сведения см. в разделе [Структуры](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="d827d-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="d827d-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="d827d-111">Examples</span></span>

<span data-ttu-id="d827d-112">Примеры и дополнительные сведения см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="d827d-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d827d-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d827d-113">C# language specification</span></span>

<span data-ttu-id="d827d-114">Примеры см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="d827d-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d827d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d827d-115">See also</span></span>

- [<span data-ttu-id="d827d-116">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d827d-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d827d-117">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="d827d-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="d827d-118">Типы значений</span><span class="sxs-lookup"><span data-stu-id="d827d-118">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="d827d-119">class</span><span class="sxs-lookup"><span data-stu-id="d827d-119">class</span></span>](class.md)
- [<span data-ttu-id="d827d-120">interface</span><span class="sxs-lookup"><span data-stu-id="d827d-120">interface</span></span>](interface.md)
- [<span data-ttu-id="d827d-121">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="d827d-121">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
