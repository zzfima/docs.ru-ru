---
title: struct. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 1f1c512e1995df07fc4b9e18e34a85119e270bda
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433781"
---
# <a name="struct-c-reference"></a><span data-ttu-id="913c6-102">struct (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="913c6-102">struct (C# Reference)</span></span>

<span data-ttu-id="913c6-103">Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="913c6-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="913c6-104">В следующем примере показано простое объявление структуры:</span><span class="sxs-lookup"><span data-stu-id="913c6-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="913c6-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="913c6-105">Remarks</span></span>

<span data-ttu-id="913c6-106">Структуры также могут содержать [конструкторы](../../programming-guide/classes-and-structs/constructors.md), [константы](../../programming-guide/classes-and-structs/constants.md), [поля](../../programming-guide/classes-and-structs/fields.md), [методы](../../programming-guide/classes-and-structs/methods.md), [свойства](../../programming-guide/classes-and-structs/properties.md), [индексаторы](../../programming-guide/indexers/index.md), [операторы](../../programming-guide/statements-expressions-operators/operators.md), [события](../../programming-guide/events/index.md) и [вложенные типы](../../programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.</span><span class="sxs-lookup"><span data-stu-id="913c6-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../../programming-guide/statements-expressions-operators/operators.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="913c6-107">Примеры см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="913c6-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="913c6-108">Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры.</span><span class="sxs-lookup"><span data-stu-id="913c6-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="913c6-109">По этой причине члены структуры не могут объявляться как `protected`.</span><span class="sxs-lookup"><span data-stu-id="913c6-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="913c6-110">Дополнительные сведения см. в разделе [Структуры](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="913c6-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="913c6-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="913c6-111">Examples</span></span>

<span data-ttu-id="913c6-112">Примеры и дополнительные сведения см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="913c6-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="913c6-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="913c6-113">C# language specification</span></span>

<span data-ttu-id="913c6-114">Примеры см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="913c6-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="913c6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="913c6-115">See also</span></span>

- [<span data-ttu-id="913c6-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="913c6-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="913c6-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="913c6-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="913c6-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="913c6-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="913c6-119">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="913c6-119">Default Values Table</span></span>](default-values-table.md)
- [<span data-ttu-id="913c6-120">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="913c6-120">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="913c6-121">Типы</span><span class="sxs-lookup"><span data-stu-id="913c6-121">Types</span></span>](types.md)
- [<span data-ttu-id="913c6-122">Типы значений</span><span class="sxs-lookup"><span data-stu-id="913c6-122">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="913c6-123">class</span><span class="sxs-lookup"><span data-stu-id="913c6-123">class</span></span>](class.md)
- [<span data-ttu-id="913c6-124">interface</span><span class="sxs-lookup"><span data-stu-id="913c6-124">interface</span></span>](interface.md)
- [<span data-ttu-id="913c6-125">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="913c6-125">Classes and Structs</span></span>](../../programming-guide/classes-and-structs/index.md)
