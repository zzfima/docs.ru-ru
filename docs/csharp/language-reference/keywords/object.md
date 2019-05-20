---
title: object. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: 99ce5300d06c500d2e45897a6bd57153dc40d34e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633386"
---
# <a name="object-c-reference"></a><span data-ttu-id="e8fc4-102">object (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e8fc4-102">object (C# Reference)</span></span>

<span data-ttu-id="e8fc4-103">Тип `object` является псевдонимом <xref:System.Object> в .NET.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-103">The `object` type is an alias for <xref:System.Object> in .NET.</span></span> <span data-ttu-id="e8fc4-104">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="e8fc4-105">Переменным типа `object` можно назначать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="e8fc4-106">Если переменная типа значения преобразуется в объект, она считается *упакованной*.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="e8fc4-107">Если переменная типа значения преобразуется в тип значения, она считается *распакованной*.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="e8fc4-108">Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="e8fc4-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>

## <a name="example"></a><span data-ttu-id="e8fc4-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e8fc4-109">Example</span></span>

<span data-ttu-id="e8fc4-110">В следующем примере показано, как переменные типа `object` могут принимать значения любого типа данных и как переменные типа `object` могут применять методы к <xref:System.Object> из платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8fc4-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>

[!code-csharp[csrefKeywordsTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#16)]

## <a name="c-language-specification"></a><span data-ttu-id="e8fc4-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e8fc4-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e8fc4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e8fc4-112">See also</span></span>

- [<span data-ttu-id="e8fc4-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e8fc4-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e8fc4-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e8fc4-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e8fc4-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e8fc4-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e8fc4-116">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="e8fc4-116">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="e8fc4-117">Типы значений</span><span class="sxs-lookup"><span data-stu-id="e8fc4-117">Value Types</span></span>](value-types.md)
