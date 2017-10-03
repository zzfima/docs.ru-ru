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
ms.lasthandoff: 09/25/2017

---
# <a name="get-c-reference"></a>get (Справочник по C#)

Ключевое слово `get` определяет *метод доступа* в свойстве или индексаторе, который возвращает значение свойства или элемент индексатора. Дополнительные сведения см. в разделах [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) и [Индексаторы](../../../csharp/programming-guide/indexers/index.md).  
  
В приведенном ниже примере определен как метод доступа `get`, так и метод доступа `set` для свойства с именем `Seconds`. Для возвращения значения свойства в нем используется закрытое поле с именем `_seconds`.  
 
 [!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Метод доступа `get` часто состоит из одного оператора, который возвращает значение, как в предыдущем примере. Начиная с версии 7 языка C# метод доступа `get` можно реализовывать как член, воплощающий выражение. В приведенном ниже примере методы доступа `get` и `set` реализуются как члены, воплощающие выражение.

 [!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
В простых случаях, когда методы доступа `get` и `set` свойства не выполняют никаких иных операций, кроме задания или извлечения значения в закрытом поле, можно использовать поддержку автоматически реализуемых свойств в компиляторе C#. В приведенном ниже примере `Hours` реализуется как автоматически реализуемое свойство. 
  
 [!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)

