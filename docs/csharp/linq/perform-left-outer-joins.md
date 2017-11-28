---
title: "Выполнение левых внешних соединений"
description: "Сведения о выполнении левых внешних соединений."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 0c28c85bf933a411403aefcb91801d28fe1c268e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="perform-left-outer-joins"></a>Выполнение левых внешних соединений
Левое внешнее соединение — это соединение, при котором каждый элемент первой коллекции возвращается независимо от наличия взаимосвязанных элементов во второй коллекции. LINQ можно использовать для левого внешнего соединения, вызвав метод <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> на основании результатов группового соединения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как использовать метод <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> применительно к результатам группового соединения для выполнения левого внешнего соединения.  
  
 Первым шагом выполнения левого внешнего соединения двух коллекций является выполнение внутреннего соединения с помощью группового соединения. (Описание этой процедуры см. в разделе [Выполнение внутренних соединений](perform-inner-joins.md).) В этом примере список объектов `Person` соединен посредством внутреннего соединения со списком объектов `Pet` на основе объекта `Person`, соответствующего `Pet.Owner`.  
  
 Вторым шагом является включение каждого элемента первой (левой) коллекции в набор результатов, даже если элемент не имеет совпадений в правой коллекции. Эта процедура выполняется путем вызова метода <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> для каждой последовательности совпадающих элементов из группового соединения. В этом примере <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> вызывается для каждой последовательности совпадающих объектов `Pet`. Метод возвращает коллекцию, содержащую одно значение по умолчанию, если последовательность соответствующих объектов `Pet` пуста для любого объекта `Person`, обеспечивая представление каждого объекта `Person` в коллекции результатов.  
  
> [!NOTE]
>  Значение по умолчанию для ссылочного типа — `null`, поэтому в примере проверяется пустая ссылка перед доступом к каждому элементу в каждой коллекции `Pet`.  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a>См. также  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [Выполнение внутренних соединений](perform-inner-joins.md)  
 [Выполнение групповых соединений](perform-grouped-joins.md)  
 [Анонимные типы](../programming-guide/classes-and-structs/anonymous-types.md)  
 
