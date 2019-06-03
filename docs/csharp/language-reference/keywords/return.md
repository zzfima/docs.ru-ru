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
ms.openlocfilehash: 3e89f2f854d1f66ca2d7bf1cfa5a507c267798f8
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422723"
---
# <a name="return-c-reference"></a><span data-ttu-id="ec967-102">return (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ec967-102">return (C# Reference)</span></span>

<span data-ttu-id="ec967-103">Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу.</span><span class="sxs-lookup"><span data-stu-id="ec967-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="ec967-104">Он также возвращает необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="ec967-104">It can also return an optional value.</span></span> <span data-ttu-id="ec967-105">Если метод имеет тип `void`, оператор `return` можно опустить.</span><span class="sxs-lookup"><span data-stu-id="ec967-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="ec967-106">Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="ec967-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="ec967-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ec967-107">Example</span></span>

 <span data-ttu-id="ec967-108">В приведенном ниже примере метод `CalculateArea()` возвращает локальную переменную `area` в виде значения [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="ec967-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](double.md) value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="ec967-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ec967-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ec967-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ec967-110">See also</span></span>

- [<span data-ttu-id="ec967-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ec967-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ec967-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ec967-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ec967-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ec967-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ec967-114">Оператор return</span><span class="sxs-lookup"><span data-stu-id="ec967-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
