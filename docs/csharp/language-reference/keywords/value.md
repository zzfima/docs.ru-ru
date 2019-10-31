---
title: Справочник по C#. Контекстное ключевое слово value
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 34b192d17bd96b6b893c9f14f0d4a77274a32f78
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771742"
---
# <a name="value-c-reference"></a><span data-ttu-id="0c388-102">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0c388-102">value (C# Reference)</span></span>

<span data-ttu-id="0c388-103">Контекстное ключевое слово `value` используется в методе доступа `set` в объявлениях [свойства](../../programming-guide/classes-and-structs/properties.md) и [индексатора](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c388-103">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="0c388-104">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="0c388-104">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="0c388-105">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству или индексатору.</span><span class="sxs-lookup"><span data-stu-id="0c388-105">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="0c388-106">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="0c388-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="0c388-107">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="0c388-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="0c388-108">Дополнительные сведения см. в статьях [Свойства](../../programming-guide/classes-and-structs/properties.md) и [Индексаторы](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c388-108">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0c388-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0c388-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0c388-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0c388-110">See also</span></span>

- [<span data-ttu-id="0c388-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0c388-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0c388-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0c388-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0c388-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0c388-113">C# Keywords</span></span>](index.md)
