---
title: . Справочник по C#. Оператор -
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a59f69d0349a054c8c2a5b701b8f63df113a6580
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333724"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="61d19-103">.</span><span class="sxs-lookup"><span data-stu-id="61d19-103">.</span></span> <span data-ttu-id="61d19-104">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="61d19-104">operator (C# Reference)</span></span>

<span data-ttu-id="61d19-105">Оператор "точка" (`.`) используется для доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="61d19-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="61d19-106">Он определяет член типа или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="61d19-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="61d19-107">Например, оператор "точка" используется для доступа к определенным методам в библиотеках классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61d19-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>

[!code-csharp[csRefOperators#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#16)]

<span data-ttu-id="61d19-108">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="61d19-108">For example, consider the following class:</span></span>

[!code-csharp[csRefOperators#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#17)]

[!code-csharp[csRefOperators#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#18)]

<span data-ttu-id="61d19-109">Переменная `s` имеет два члена: `a` и `b`. Чтобы получить к ним доступ, используйте оператор "точка".</span><span class="sxs-lookup"><span data-stu-id="61d19-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>

[!code-csharp[csRefOperators#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#19)]

<span data-ttu-id="61d19-110">Точка также используется для формирования полных имен, указывающих пространство имен или интерфейс, к которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="61d19-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>

[!code-csharp[csRefOperators#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#20)]

<span data-ttu-id="61d19-111">Директива using делает уточнение некоторых имен необязательным.</span><span class="sxs-lookup"><span data-stu-id="61d19-111">The using directive makes some name qualification optional:</span></span>

[!code-csharp[csRefOperators#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#21)]

<span data-ttu-id="61d19-112">Однако в случае неоднозначного идентификатора имя должно быть полным.</span><span class="sxs-lookup"><span data-stu-id="61d19-112">But when an identifier is ambiguous, it must be qualified:</span></span>

[!code-csharp[csRefOperators#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="61d19-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="61d19-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="61d19-114">См. также</span><span class="sxs-lookup"><span data-stu-id="61d19-114">See also</span></span>

- [<span data-ttu-id="61d19-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="61d19-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="61d19-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="61d19-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="61d19-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="61d19-117">C# Operators</span></span>](index.md)