---
title: return (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 1b6a1ce2a8587c8630fece3d5c9a2186fbbc9c22
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001480"
---
# <a name="return-c-reference"></a><span data-ttu-id="0d4f6-102">return (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0d4f6-102">return (C# Reference)</span></span>
<span data-ttu-id="0d4f6-103">Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу.</span><span class="sxs-lookup"><span data-stu-id="0d4f6-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="0d4f6-104">Он также возвращает необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="0d4f6-104">It can also return an optional value.</span></span> <span data-ttu-id="0d4f6-105">Если метод имеет тип `void`, оператор `return` можно опустить.</span><span class="sxs-lookup"><span data-stu-id="0d4f6-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="0d4f6-106">Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="0d4f6-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d4f6-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0d4f6-107">Example</span></span>  
 <span data-ttu-id="0d4f6-108">В приведенном ниже примере метод `CalculateArea()` возвращает локальную переменную `area` в виде значения [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="0d4f6-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d4f6-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0d4f6-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d4f6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0d4f6-110">See Also</span></span>

- [<span data-ttu-id="0d4f6-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0d4f6-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0d4f6-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0d4f6-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0d4f6-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0d4f6-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="0d4f6-114">Оператор return</span><span class="sxs-lookup"><span data-stu-id="0d4f6-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
- [<span data-ttu-id="0d4f6-115">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="0d4f6-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
