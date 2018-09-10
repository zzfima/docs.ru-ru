---
title: Предложение let (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 62294df7f0f2ebb3249dffd72ba4910fbae984c8
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266632"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="cdae8-102">Предложение let (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cdae8-102">let clause (C# Reference)</span></span>

<span data-ttu-id="cdae8-103">В выражении запроса иногда требуется сохранить результат вложенного выражения, который будет использоваться в последующих предложениях.</span><span class="sxs-lookup"><span data-stu-id="cdae8-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="cdae8-104">Это можно сделать с помощью ключевого слова `let`, которое создает новую переменную диапазона и инициализирует ее, используя результат предоставленного выражения.</span><span class="sxs-lookup"><span data-stu-id="cdae8-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="cdae8-105">После инициализации с использованием этого значения такую переменную диапазона нельзя использовать для хранения других значений.</span><span class="sxs-lookup"><span data-stu-id="cdae8-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="cdae8-106">Тем не менее если переменная диапазона хранит запрашиваемый тип, к ней можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="cdae8-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="cdae8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cdae8-107">Example</span></span>

<span data-ttu-id="cdae8-108">В следующем примере показываются два способа использования `let`:</span><span class="sxs-lookup"><span data-stu-id="cdae8-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="cdae8-109">Создание перечисляемого типа, к которому можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="cdae8-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="cdae8-110">Реализация запроса с однократным вызовом `ToLower` для переменной диапазона `word`.</span><span class="sxs-lookup"><span data-stu-id="cdae8-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="cdae8-111">Если ключевое слово `let` не используется, потребуется выполнять вызов `ToLower` в каждом предикате предложения `where`.</span><span class="sxs-lookup"><span data-stu-id="cdae8-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="cdae8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cdae8-112">See also</span></span>

- [<span data-ttu-id="cdae8-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="cdae8-113">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="cdae8-114">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cdae8-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="cdae8-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="cdae8-115">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="cdae8-116">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="cdae8-116">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="cdae8-117">Обработка исключений в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="cdae8-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)