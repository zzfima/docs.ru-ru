---
title: '@. Справочник по C#'
ms.custom: seodec18
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: 6f9f16b2639cd9ea57ee7a3030deabf4c1decfbb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101561"
---
# <a name="-c-reference"></a><span data-ttu-id="3e143-102">@ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3e143-102">@ (C# Reference)</span></span>

<span data-ttu-id="3e143-103">Специальный символ `@` является буквальным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="3e143-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="3e143-104">Его можно применять в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="3e143-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="3e143-105">Чтобы использовать ключевые слова C# в качестве идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="3e143-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="3e143-106">Символ `@` предшествует элементу кода, который компилятор должен интерпретировать как идентификатор, а не ключевое слово C#.</span><span class="sxs-lookup"><span data-stu-id="3e143-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="3e143-107">В следующем примере символ `@` используется для определения идентификатора `for`, используемого в цикле `for`.</span><span class="sxs-lookup"><span data-stu-id="3e143-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="3e143-108">Чтобы указать, что строковый литерал следует интерпретировать буквально.</span><span class="sxs-lookup"><span data-stu-id="3e143-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="3e143-109">Символ `@` в этом случае определяет *буквальный строковый литерал*.</span><span class="sxs-lookup"><span data-stu-id="3e143-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="3e143-110">Простые escape-последовательности (например, `"\\"` для обратной косой черты), шестнадцатеричные escape-последовательности (например, `"\x0041"` для прописной буквы A) и escape-последовательности Юникода (например, `"\u0041"` для прописной буквы A) интерпретируются буквально.</span><span class="sxs-lookup"><span data-stu-id="3e143-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="3e143-111">Только escape-последовательность кавычек (`""`) не интерпретируется буквально; она создает одну кавычку.</span><span class="sxs-lookup"><span data-stu-id="3e143-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="3e143-112">Кроме того, в случае буквальной [интерполированной строки](interpolated.md) escape-последовательности фигурных скобок (`{{` и `}}`) не интерпретируются буквально; они создают одну фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="3e143-112">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="3e143-113">В следующем примере определяются два идентичных пути к файлам: один с помощью обычного строкового литерала, а другой — с помощью буквального строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="3e143-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="3e143-114">Это один из наиболее распространенных способов использования буквальных строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="3e143-114">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="3e143-115">В следующем примере показан результат определения обычного строкового литерала и буквального строкового литерала, содержащий идентичные последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="3e143-115">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="3e143-116">Чтобы позволить компилятору различать атрибуты в случае конфликта имен.</span><span class="sxs-lookup"><span data-stu-id="3e143-116">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="3e143-117">Атрибут класса, который наследует от <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="3e143-117">An attribute is a class that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="3e143-118">Имя его типа, как правило, содержит суффикс **Attribute**, несмотря на то, что компилятор не выполняет это соглашение.</span><span class="sxs-lookup"><span data-stu-id="3e143-118">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="3e143-119">Затем на атрибут можно ссылаться в коде либо по его полному имени типа (например, `[InfoAttribute]`), либо по сокращенному имени (например, `[Info]`).</span><span class="sxs-lookup"><span data-stu-id="3e143-119">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="3e143-120">Однако если два сокращенных имени типов совпадают и одно имя типа содержит суффикс **Attribute**, а другое — нет, возникает конфликт имен.</span><span class="sxs-lookup"><span data-stu-id="3e143-120">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="3e143-121">Например, приведенный ниже код не может быть скомпилирован, так как компилятору не удается определить, какой атрибут — `Info` или `InfoAttribute` — применен к классу `Example`.</span><span class="sxs-lookup"><span data-stu-id="3e143-121">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span> <span data-ttu-id="3e143-122">См. [CS1614](../compiler-messages/cs1614.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="3e143-122">See [CS1614](../compiler-messages/cs1614.md) for more information.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a><span data-ttu-id="3e143-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3e143-123">See also</span></span>

- [<span data-ttu-id="3e143-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3e143-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3e143-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3e143-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3e143-126">Специальные символы в C#</span><span class="sxs-lookup"><span data-stu-id="3e143-126">C# Special Characters</span></span>](./index.md)
