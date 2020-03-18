---
title: get. Справочник по C#
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: 61d8c02aaf13f43ff8ea17c1e868ea9fd52893c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173631"
---
# <a name="get-c-reference"></a><span data-ttu-id="6ca83-102">get (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6ca83-102">get (C# Reference)</span></span>

<span data-ttu-id="6ca83-103">Ключевое слово `get` определяет *метод доступа* в свойстве или индексаторе, который возвращает значение свойства или элемент индексатора.</span><span class="sxs-lookup"><span data-stu-id="6ca83-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="6ca83-104">Дополнительные сведения см. в разделах [Свойства](../../programming-guide/classes-and-structs/properties.md), [Автоматически реализуемые свойства](../../programming-guide/classes-and-structs/auto-implemented-properties.md) и [Индексаторы](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6ca83-104">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="6ca83-105">В приведенном ниже примере определен как метод доступа `get`, так и метод доступа `set` для свойства с именем `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="6ca83-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="6ca83-106">Для возвращения значения свойства в нем используется закрытое поле с именем `_seconds`.</span><span class="sxs-lookup"><span data-stu-id="6ca83-106">It uses a private field named `_seconds` to back the property value.</span></span>  

 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="6ca83-107">Метод доступа `get` часто состоит из одного оператора, который возвращает значение, как в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="6ca83-107">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="6ca83-108">Начиная с C# версии 7.0 метод доступа `get` можно реализовывать как член, воплощающий выражение.</span><span class="sxs-lookup"><span data-stu-id="6ca83-108">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="6ca83-109">В приведенном ниже примере методы доступа `get` и `set` реализуются как члены, воплощающие выражение.</span><span class="sxs-lookup"><span data-stu-id="6ca83-109">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]

<span data-ttu-id="6ca83-110">В простых случаях, когда методы доступа `get` и `set` свойства не выполняют никаких иных операций, кроме задания или извлечения значения в закрытом поле, можно использовать поддержку автоматически реализуемых свойств в компиляторе C#.</span><span class="sxs-lookup"><span data-stu-id="6ca83-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="6ca83-111">В приведенном ниже примере `Hours` реализуется как автоматически реализуемое свойство.</span><span class="sxs-lookup"><span data-stu-id="6ca83-111">The following example implements `Hours` as an auto-implemented property.</span></span>
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ca83-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6ca83-112">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ca83-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6ca83-113">See also</span></span>

- [<span data-ttu-id="6ca83-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6ca83-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6ca83-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6ca83-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6ca83-116">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6ca83-116">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="6ca83-117">Свойства</span><span class="sxs-lookup"><span data-stu-id="6ca83-117">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
