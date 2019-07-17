---
title: Справочник по C#. Оператор return
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: a845ce257bf7f0cf0e64d6815b2278f6cec946e7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661617"
---
# <a name="return-c-reference"></a><span data-ttu-id="0d6d9-102">return (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0d6d9-102">return (C# Reference)</span></span>

<span data-ttu-id="0d6d9-103">Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу.</span><span class="sxs-lookup"><span data-stu-id="0d6d9-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="0d6d9-104">Он также возвращает необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="0d6d9-104">It can also return an optional value.</span></span> <span data-ttu-id="0d6d9-105">Если метод имеет тип `void`, оператор `return` можно опустить.</span><span class="sxs-lookup"><span data-stu-id="0d6d9-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="0d6d9-106">Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="0d6d9-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="0d6d9-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0d6d9-107">Example</span></span>

 <span data-ttu-id="0d6d9-108">В приведенном ниже примере метод `CalculateArea()` возвращает локальную переменную `area` в виде значения `double`.</span><span class="sxs-lookup"><span data-stu-id="0d6d9-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="0d6d9-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0d6d9-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0d6d9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0d6d9-110">See also</span></span>

- [<span data-ttu-id="0d6d9-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0d6d9-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0d6d9-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0d6d9-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0d6d9-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0d6d9-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0d6d9-114">Оператор return</span><span class="sxs-lookup"><span data-stu-id="0d6d9-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
