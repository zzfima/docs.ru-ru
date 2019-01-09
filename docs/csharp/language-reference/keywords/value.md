---
title: Справочник по C#. Контекстное ключевое слово value
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ee80888a57e999fa44e891dd6e0d64caa698009c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612066"
---
# <a name="value-c-reference"></a><span data-ttu-id="0b7e7-102">value (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0b7e7-102">value (C# Reference)</span></span>

<span data-ttu-id="0b7e7-103">Контекстное ключевое слово `value` используется в методе доступа set в обычных объявлениях свойств.</span><span class="sxs-lookup"><span data-stu-id="0b7e7-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="0b7e7-104">Оно аналогично входному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="0b7e7-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="0b7e7-105">Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.</span><span class="sxs-lookup"><span data-stu-id="0b7e7-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="0b7e7-106">В приведенном ниже примере класс `MyDerivedClass` имеет свойство с именем `Name`, в котором используется параметр `value` для присвоения новой строки резервному полю `name`.</span><span class="sxs-lookup"><span data-stu-id="0b7e7-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="0b7e7-107">С точки зрения клиентского кода эта операция выглядит как простое присвоение.</span><span class="sxs-lookup"><span data-stu-id="0b7e7-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="0b7e7-108">Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="0b7e7-108">For more information about the use of `value`, see [Properties](../../programming-guide/classes-and-structs/properties.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b7e7-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0b7e7-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0b7e7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0b7e7-110">See also</span></span>

- [<span data-ttu-id="0b7e7-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0b7e7-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0b7e7-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0b7e7-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0b7e7-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0b7e7-113">C# Keywords</span></span>](index.md)