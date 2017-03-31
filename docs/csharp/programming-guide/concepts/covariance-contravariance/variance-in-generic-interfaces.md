---
title: "Вариативность в универсальных интерфейсах (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4c4f3ab00b4de2a6f38858dd5f332db3d47eb85b
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-c"></a>Вариативность в универсальных интерфейсах (C#)
В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы. Сейчас вариативными являются следующие интерфейсы.  
  
-   <xref:System.Collections.Generic.IEnumerable%601> (T является ковариантным интерфейсом)  
  
-   <xref:System.Collections.Generic.IEnumerator%601> (T является ковариантным интерфейсом)  
  
-   <xref:System.Linq.IQueryable%601> (T является ковариантным интерфейсом)  
  
-   <xref:System.Linq.IGrouping%602> (`TKey` и `TElement` являются ковариантными интерфейсами)  
  
-   <xref:System.Collections.Generic.IComparer%601> (T является ковариантным интерфейсом)  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601> (T является ковариантным интерфейсом)  
  
-   <xref:System.IComparable%601> (T является ковариантным интерфейсом)  
  
 Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметре универсального типа интерфейса. Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable<Object>` и `IEnumerable<String>`. Интерфейс `IEnumerable<String>` не наследует интерфейс `IEnumerable<Object>`. При этом тип `String` наследует тип `Object`, и в некоторых случаях может потребоваться назначить объекты этих интерфейсов друг другу. Это показано в следующем примере кода.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 В более ранних версиях .NET Framework этот код приводит к ошибке компиляции в C# в `Option Strict On`. Но теперь можно использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку интерфейс <xref:System.Collections.Generic.IEnumerable%601> является ковариантным.  
  
 Контравариантность позволяет методу иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа интерфейса. Чтобы продемонстрировать функцию контравариантности, предположим, что создан класса `BaseComparer` для сравнения экземпляров класса `BaseClass`. Класс `BaseComparer` реализует интерфейс `IEqualityComparer<BaseClass>`. Поскольку теперь интерфейс <xref:System.Collections.Generic.IEqualityComparer%601> является контравариантным, можно использовать класс `BaseComparer` для сравнения экземпляров классов, наследующих класс `BaseClass`. Это показано в следующем примере кода.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Дополнительные примеры см.в разделе [Использование вариативности в интерфейсах для универсальных коллекций (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов. Типы значений не поддерживают вариативность. Например, `IEnumerable<int>` нельзя неявно преобразовать в `IEnumerable<object>`, так как типом значения является integer.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Кроме того, важно помнить, что классы, которые реализуют вариативные интерфейсы, сами являются инвариантными. Например, несмотря на то что <xref:System.Collections.Generic.List%601> реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, нельзя неявно преобразовать `List<Object>` в `List<String>`. Это показано в следующем примере кода.  
  
```cs  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a>См. также  
 [Использование вариативности в интерфейсах для универсальных коллекций (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Создание вариативных универсальных интерфейсов (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Универсальные интерфейсы](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [Вариативность в делегатах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
