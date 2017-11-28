---
title: "Универсальные делегаты. (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1377723f18d6dd0e984538b530acbc7aa8d52feb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="generic-delegates-c-programming-guide"></a>Универсальные делегаты. (Руководство по программированию на C#)
[Делегат](../../../csharp/language-reference/keywords/delegate.md) может определять собственные параметры типа. В коде, который ссылается на универсальный делегат, можно указать аргумент типа для создания закрытого сконструированного типа. Это будет аналогично созданию экземпляра универсального класса или вызову универсального метода, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 В C# версии 2.0 представлена новая функция группового преобразования методов, которая применяется как к конкретным, так и к универсальным типам делегатов, и позволяет записать приведенную выше строку с использованием упрощенного синтаксиса:  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 Делегаты, определенные в универсальном классе, могут использовать параметры класса универсального типа таким же образом, как это делают методы класса.  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 В коде, который ссылается на делегат, необходимо указать аргумент типа содержащего класса, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 Универсальные делегаты особенно полезны при определении событий, основанных на типовых шаблонах разработки, поскольку аргумент отправителя может быть строго типизирован и больше не требует приведения к <xref:System.Object> и из него.  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md)  
 [Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md)  
 [Универсальные интерфейсы](../../../csharp/programming-guide/generics/generic-interfaces.md)  
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
 [Универсальные шаблоны](~/docs/standard/generics/index.md)
