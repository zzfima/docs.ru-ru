---
title: разделяемый тип (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 365d00d2c53d3efe1cd4330bdd3ec48740a49c53
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586584"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="7bb83-102">разделяемый тип (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7bb83-102">partial type (C# Reference)</span></span>

<span data-ttu-id="7bb83-103">Определения разделяемых типов позволяют разделять определения классов, структур и интерфейсов на несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="7bb83-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="7bb83-104">В файле *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="7bb83-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="7bb83-105">Объявление в файле *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="7bb83-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="7bb83-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bb83-106">Remarks</span></span>

<span data-ttu-id="7bb83-107">Разделение типа класса, структуры или интерфейса на несколько файлов может пригодиться при работе с крупными проектами или с автоматически созданным кодом, например предоставляемым [конструктором Windows Forms](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="7bb83-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="7bb83-108">Разделяемый тип может содержать [разделяемый метод](partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="7bb83-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="7bb83-109">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7bb83-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7bb83-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7bb83-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7bb83-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7bb83-111">See also</span></span>

- [<span data-ttu-id="7bb83-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7bb83-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7bb83-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7bb83-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7bb83-114">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="7bb83-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="7bb83-115">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="7bb83-115">Introduction to Generics</span></span>](../../programming-guide/generics/introduction-to-generics.md)