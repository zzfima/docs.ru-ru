---
title: Справочник по C#. Контекстное ключевое слово global
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 9a8c7b5134cc29668aae53e8a3f86ddae4c8263a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627681"
---
# <a name="global-c-reference"></a><span data-ttu-id="cb16a-102">global (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cb16a-102">global (C# Reference)</span></span>

<span data-ttu-id="cb16a-103">Контекстное слово `global`, указанное перед [оператором ::](../operators/namespace-alias-qualifier.md), ссылается на глобальное пространство имен, которое используется по умолчанию в любых программах на языке C# и в других случаях не именуется отдельно.</span><span class="sxs-lookup"><span data-stu-id="cb16a-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifier.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="cb16a-104">Дополнительные сведения см. в разделе [Практическое руководство. использованию псевдонима глобального пространства имен](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="cb16a-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="cb16a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="cb16a-105">Example</span></span>

<span data-ttu-id="cb16a-106">В следующем примере показано, как использовать контекстное ключевое слово `global`, чтобы указать, что класс `TestApp` определен в глобальном пространстве имен:</span><span class="sxs-lookup"><span data-stu-id="cb16a-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="cb16a-107">См. также</span><span class="sxs-lookup"><span data-stu-id="cb16a-107">See also</span></span>

- [<span data-ttu-id="cb16a-108">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="cb16a-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
