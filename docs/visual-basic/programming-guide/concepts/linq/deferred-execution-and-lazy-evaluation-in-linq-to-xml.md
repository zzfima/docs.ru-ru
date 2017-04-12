---
title: "Отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3b7318eb9853d633d152b93fafcf9570ccd03835
ms.lasthandoff: 03/13/2017


---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a>Отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic)
Операции по обработке запросов и осей часто реализуются с использованием отложенного выполнения. В этом разделе разъясняются требования и достоинства отложенного выполнения, а также содержатся некоторые соображения относительно реализации.  
  
## <a name="deferred-execution"></a>Отложенное выполнение  
 Отложенное выполнение означает, что вычисление выражения откладывается до его *понял* действительно требуется значение. Отложенное выполнение может значительно повышать производительность в ситуациях, когда приходится манипулировать большими коллекциями данных, особенно в программах, содержащих ряд последовательных запросов или манипуляций. В лучшем случае отложенное выполнение обеспечивает только один проход по исходной коллекции.  
  
 Технологии LINQ предусматривают широкое использование отложенного выполнения в членах основных <xref:System.Linq?displayProperty=fullName>классы и методы расширения в различных пространствах имен LINQ, таких как <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</xref:System.Xml.Linq.Extensions?displayProperty=fullName> </xref:System.Linq?displayProperty=fullName>  
  
## <a name="eager-vs-lazy-evaluation"></a>Сравнение безотложного  и отложенного вычислений  
 При создании метода, реализующего отложенное выполнение, необходимо также решать вопрос о том, следует ли реализовывать этот метод с помощью отложенного или безотложного вычисления.  
  
-   В *отложенное вычисление*, один элемент исходной коллекции обрабатывается при каждом обращении к итератору. Это типичный способ реализации итераторов.  
  
-   В *безотложного вычисления*, приведет к первого вызова к итератору обрабатывается вся коллекция. Может также потребоваться временная копия исходной коллекции. Например <xref:System.Linq.Enumerable.OrderBy%2A>метод должен отсортировать всю коллекцию, перед тем как возвратить первый элемент.</xref:System.Linq.Enumerable.OrderBy%2A>  
  
 Метод неспешного вычисления обычно обеспечивает более высокую производительность, поскольку он равномерно распределяет затраты на обработку по всему периоду вычисления и сводит к минимуму использование временных данных. Разумеется, при выполнении некоторых операций не остается ничего иного, как материализовать промежуточные результаты.  
  
## <a name="next-steps"></a>Следующие шаги  
 Следующий раздел настоящего учебника иллюстрирует отложенное выполнение:  
  
-   [Пример отложенного выполнения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник: Отложенного выполнения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)   
 [Основные понятия и терминология (функциональное преобразование) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)   
 [Операции статистической обработки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
