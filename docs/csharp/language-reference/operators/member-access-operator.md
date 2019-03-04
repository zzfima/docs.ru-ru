---
title: . Справочник по C#. Оператор -
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836465"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="08f89-103">.</span><span class="sxs-lookup"><span data-stu-id="08f89-103">.</span></span> <span data-ttu-id="08f89-104">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="08f89-104">operator (C# Reference)</span></span>

<span data-ttu-id="08f89-105">Оператор "точка" (`.`) обычно используется для доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="08f89-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="08f89-106">Маркер `.` используется для обращения к члену пространства имен или типа, как в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="08f89-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="08f89-107">Используйте `.` для обращения к пространству имен, вложенному в другое пространство имен, как показано в следующем примере [директивы `using`](../keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="08f89-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="08f89-108">Используйте `.` для создания *полного имени* для обращения к типу в пределах пространства имен, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="08f89-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="08f89-109">Используйте [директиву `using`](../keywords/using-directive.md), чтобы сделать использование полных имен необязательным.</span><span class="sxs-lookup"><span data-stu-id="08f89-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="08f89-110">Используйте `.` для обращения к [членам типов](../../programming-guide/classes-and-structs/index.md#members) (статическим и нестатическим), как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="08f89-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="08f89-111">Можно также использовать `.` для вызова [метода расширения](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="08f89-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="08f89-112">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="08f89-112">Operator overloadability</span></span>

<span data-ttu-id="08f89-113">Оператор `.` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="08f89-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="08f89-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="08f89-114">C# language specification</span></span>

<span data-ttu-id="08f89-115">Дополнительные сведения см. в разделе [Доступ к членам](~/_csharplang/spec/expressions.md#member-access) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="08f89-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="08f89-116">См. также</span><span class="sxs-lookup"><span data-stu-id="08f89-116">See also</span></span>

- [<span data-ttu-id="08f89-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="08f89-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="08f89-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="08f89-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="08f89-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="08f89-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="08f89-120">[Операторы ?. и ?[]](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="08f89-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>