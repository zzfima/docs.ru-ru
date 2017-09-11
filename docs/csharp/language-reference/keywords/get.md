---
title: "get (Справочник по C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
dev_langs:
- CSharp
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 88603864ae0a31a193cab211b8ce8061ec63c169
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="get-c-reference"></a><span data-ttu-id="339d4-102">get (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="339d4-102">get (C# Reference)</span></span>

<span data-ttu-id="339d4-103">Ключевое слово `get` определяет *метод доступа* в свойстве или индексаторе, который возвращает значение свойства или элемент индексатора.</span><span class="sxs-lookup"><span data-stu-id="339d4-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="339d4-104">Дополнительные сведения см. в разделах [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) и [Индексаторы](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="339d4-104">For more information, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="339d4-105">В приведенном ниже примере определен как метод доступа `get`, так и метод доступа `set` для свойства с именем `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="339d4-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="339d4-106">Для возвращения значения свойства в нем используется закрытое поле с именем `_seconds`.</span><span class="sxs-lookup"><span data-stu-id="339d4-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 <span data-ttu-id="339d4-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="339d4-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span></span>  
  
<span data-ttu-id="339d4-108">Метод доступа `get` часто состоит из одного оператора, который возвращает значение, как в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="339d4-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="339d4-109">Начиная с версии 7 языка C# метод доступа `get` можно реализовывать как член, воплощающий выражение.</span><span class="sxs-lookup"><span data-stu-id="339d4-109">Starting with C# 7, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="339d4-110">В приведенном ниже примере методы доступа `get` и `set` реализуются как члены, воплощающие выражение.</span><span class="sxs-lookup"><span data-stu-id="339d4-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 <span data-ttu-id="339d4-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="339d4-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span></span>   
 
<span data-ttu-id="339d4-112">В простых случаях, когда методы доступа `get` и `set` свойства не выполняют никаких иных операций, кроме задания или извлечения значения в закрытом поле, можно использовать поддержку автоматически реализуемых свойств в компиляторе C#.</span><span class="sxs-lookup"><span data-stu-id="339d4-112">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="339d4-113">В приведенном ниже примере `Hours` реализуется как автоматически реализуемое свойство.</span><span class="sxs-lookup"><span data-stu-id="339d4-113">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 <span data-ttu-id="339d4-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="339d4-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="339d4-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="339d4-115">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="339d4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="339d4-116">See Also</span></span>  
 <span data-ttu-id="339d4-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="339d4-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="339d4-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="339d4-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="339d4-119">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)</span><span class="sxs-lookup"><span data-stu-id="339d4-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md)</span></span>

