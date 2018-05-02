---
title: get (Справочник по C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3cdf639065ee5bf0cb9e920061557991c0a4b921
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="get-c-reference"></a>get (Справочник по C#)

Ключевое слово `get` определяет *метод доступа* в свойстве или индексаторе, который возвращает значение свойства или элемент индексатора. Дополнительные сведения см. в разделах [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) и [Индексаторы](../../../csharp/programming-guide/indexers/index.md).  
  
В приведенном ниже примере определен как метод доступа `get`, так и метод доступа `set` для свойства с именем `Seconds`. Для возвращения значения свойства в нем используется закрытое поле с именем `_seconds`.  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Метод доступа `get` часто состоит из одного оператора, который возвращает значение, как в предыдущем примере. Начиная с C# версии 7.0 метод доступа `get` можно реализовывать как член, воплощающий выражение. В приведенном ниже примере методы доступа `get` и `set` реализуются как члены, воплощающие выражение.

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
В простых случаях, когда методы доступа `get` и `set` свойства не выполняют никаких иных операций, кроме задания или извлечения значения в закрытом поле, можно использовать поддержку автоматически реализуемых свойств в компиляторе C#. В приведенном ниже примере `Hours` реализуется как автоматически реализуемое свойство. 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)
