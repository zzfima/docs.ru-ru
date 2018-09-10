---
title: Анонимные функции (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 90a5a71f83a7117a7468bab0d9fe9d013685ebbe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515243"
---
# <a name="anonymous-functions-c-programming-guide"></a>Анонимные функции (Руководство по программированию на C#)
Анонимная функция — это "встроенный" оператор или выражение, которое может использоваться, когда тип делегата неизвестен. Ее можно использовать для инициализации именованного делегата или передать вместо типа именованного делегата в качестве параметра метода.  
  
 Существует два типа анонимных функций, которые по отдельности рассматриваются в следующих разделах:  
  
-   [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Лямбда-выражения могут быть привязаны к деревьям выражений и к делегатам.  
  
## <a name="the-evolution-of-delegates-in-c"></a>Эволюция делегатов в C#  
 В C# 1.0 экземпляр делегата создавался путем его явной инициализации с помощью метода, который был определен в другом месте кода. В C# 2.0 введена концепция анонимных методов как способа написания неименованных встроенных блоков операторов, которые могут быть выполнены в вызове делегата. В C# 3.0 введены лямбда-выражения, по сути аналогичные анонимным методам, но более выразительные и четкие. Эти две функции собирательно называют *анонимными функциями*. Как правило, в приложениях, предназначенных для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 и более поздних версий, следует использовать лямбда-выражения.  
  
 В следующем примере демонстрируется эволюция создания делегата от C# 1.0 до C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Инструкции, выражения и операторы](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
- [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
- [Expression Trees (C#)](../concepts/expression-trees/index.md) (Деревья выражений (C#))  
