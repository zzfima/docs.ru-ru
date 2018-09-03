---
title: Контекстное ключевое слово global (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 837245e31a9a795aa2f13cfc6c33fefb6402801d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43401078"
---
# <a name="global-c-reference"></a><span data-ttu-id="2fd77-102">global (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2fd77-102">global (C# Reference)</span></span>

<span data-ttu-id="2fd77-103">Контекстное слово `global`, указанное перед [оператором ::](../operators/namespace-alias-qualifer.md), ссылается на глобальное пространство имен, которое используется по умолчанию в любых программах на языке C# и в других случаях не именуется отдельно.</span><span class="sxs-lookup"><span data-stu-id="2fd77-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifer.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="2fd77-104">Дополнительные сведения см. в разделе [Практическое руководство. Использование псевдонима глобального пространства имен](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="2fd77-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="2fd77-105">Пример</span><span class="sxs-lookup"><span data-stu-id="2fd77-105">Example</span></span>

<span data-ttu-id="2fd77-106">В следующем примере показано, как использовать контекстное ключевое слово `global`, чтобы указать, что класс `TestApp` определен в глобальном пространстве имен:</span><span class="sxs-lookup"><span data-stu-id="2fd77-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="2fd77-107">См. также</span><span class="sxs-lookup"><span data-stu-id="2fd77-107">See also</span></span>

- [<span data-ttu-id="2fd77-108">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="2fd77-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)