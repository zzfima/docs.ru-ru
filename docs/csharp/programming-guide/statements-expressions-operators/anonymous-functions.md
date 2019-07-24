---
title: Руководство по программированию на C#. Анонимные функции
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 4d266584e1867a512e4b61e8839fe948aafb007f
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363916"
---
# <a name="anonymous-functions-c-programming-guide"></a>Руководство по программированию на C#. Анонимные функции

Анонимная функция — это "встроенный" оператор или выражение, которое может использоваться, когда тип делегата неизвестен. Ее можно использовать для инициализации именованного делегата или передать вместо типа именованного делегата в качестве параметра метода.

Для создания анонимной функции можно использовать [лямбда-выражение](lambda-expressions.md) или [анонимный метод](../../language-reference/operators/delegate-operator.md). Мы советуем использовать лямбда-выражения, так как это более лаконичный способ написания встроенного кода. В отличие от анонимных методов некоторые типы лямбда-выражений можно преобразовывать в типы дерева выражений.

## <a name="the-evolution-of-delegates-in-c"></a>Эволюция делегатов в C\#

 В C# 1.0 экземпляр делегата создавался путем его явной инициализации с помощью метода, который был определен в другом месте кода. В C# 2.0 введена концепция анонимных методов как способа написания неименованных встроенных блоков операторов, которые могут быть выполнены в вызове делегата. В C# 3.0 введены лямбда-выражения, по сути аналогичные анонимным методам, но более выразительные и четкие. Эти две функции собирательно называют *анонимными функциями*. Как правило, приложения, предназначенные для версии 3.5 и более поздних версий платформы .NET Framework, должны использовать лямбда-выражения.  
  
 В следующем примере демонстрируется эволюция создания делегата от C# 1.0 до C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>См. также

- [Инструкции, выражения и операторы](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)
- [Expression Trees (C#)](../concepts/expression-trees/index.md) (Деревья выражений (C#))
