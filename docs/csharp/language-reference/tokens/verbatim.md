---
title: "@ (справочник по C#)"
ms.date: 02/09/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30f937951557ba65971a752b414cce6b485149be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-c-reference"></a><span data-ttu-id="a6ad2-102">@ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a6ad2-102">@ (C# Reference)</span></span>

<span data-ttu-id="a6ad2-103">Специальный символ `@` является буквальным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="a6ad2-104">Его можно применять в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="a6ad2-105">Чтобы использовать ключевые слова C# в качестве идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="a6ad2-106">Символ `@` предшествует элементу кода, который компилятор должен интерпретировать как идентификатор, а не ключевое слово C#.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="a6ad2-107">В следующем примере символ `@` используется для определения идентификатора `for`, используемого в цикле `for`.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="a6ad2-108">Чтобы указать, что строковый литерал следует интерпретировать буквально.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="a6ad2-109">Символ `@` в этом экземпляре определяет *буквальный строковый литерал*.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="a6ad2-110">Простые escape-последовательности (например, `"\\"` для обратной косой черты), шестнадцатеричные escape-последовательности (например, `"\x0041"` для прописной буквы A) и escape-последовательность Юникода (например, `"\u0041"` для прописной буквы A) интерпретируются буквально.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A, and Unicode escape sequences, such as `"\u0041"` for an uppercase A, are interpreted literally.</span></span> <span data-ttu-id="a6ad2-111">Только escape-последовательность кавычки (`""`) не интерпретируется буквально; она создает одинарную кавычку.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="a6ad2-112">В следующем примере определяется два идентичных пути к файлам: один с помощью обычного строкового литерала, а другой — с помощью буквального строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-112">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="a6ad2-113">Это один из наиболее распространенных способов использования буквальных строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-113">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="a6ad2-114">В следующем примере показан результат определения обычного строкового литерала и буквального строкового литерала, содержащий идентичные последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-114">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="a6ad2-115">Чтобы позволить компилятору различать атрибуты в случае конфликта имен.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-115">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="a6ad2-116">Атрибут — это тип, производный от <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-116">An attribute is a type that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="a6ad2-117">Имя его типа, как правило, содержит суффикс **Attribute**, несмотря на то, что компилятор не выполняет это соглашение.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-117">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="a6ad2-118">Затем на атрибут можно ссылаться в коде либо по его полному имени типа (например, `[InfoAttribute]`), либо по сокращенному имени (например, `[Info]`).</span><span class="sxs-lookup"><span data-stu-id="a6ad2-118">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="a6ad2-119">Однако если два сокращенных имени типов совпадают и одно имя типа содержит суффикс **Attribute**, а другое — нет, возникает конфликт имен.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-119">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="a6ad2-120">Например, следующий код не может быть скомпилирован, поскольку компилятору не удается определить, какой атрибут — `Info` или `InfoAttribute` — применен к методу `Main`.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-120">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Main` method.</span></span>

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   <span data-ttu-id="a6ad2-121">Если для определения атрибута `Info` используется буквальный идентификатор, код компилируется успешно.</span><span class="sxs-lookup"><span data-stu-id="a6ad2-121">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a><span data-ttu-id="a6ad2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a6ad2-122">See Also</span></span>  
 [<span data-ttu-id="a6ad2-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a6ad2-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a6ad2-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a6ad2-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a6ad2-125">Специальные символы в C#</span><span class="sxs-lookup"><span data-stu-id="a6ad2-125">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)
