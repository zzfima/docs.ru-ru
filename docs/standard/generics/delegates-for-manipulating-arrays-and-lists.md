---
title: "Универсальные делегаты для управления массивами и списками | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "массивы [платформа .NET Framework], универсальные делегаты"
  - "связывание делегатов"
  - "делегаты [платформа .NET Framework], универсальные делегаты"
  - "универсальные делегаты [платформа .NET Framework]"
  - "универсальные шаблоны [платформа .NET Framework], делегаты"
  - "списки [платформа .NET Framework], универсальные делегаты"
ms.assetid: 416be383-cc61-4102-9b1b-88b51adb963e
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Универсальные делегаты для управления массивами и списками
В этом разделе содержится обзор универсальных делегатов для преобразований, предикатов поиска и действий, осуществляемых с элементами массива или коллекции.  
  
## Универсальные делегаты для управления массивами и списками  
 Универсальный делегат <xref:System.Action%601> представляет метод, выполняющий некоторое действие с элементом указанного типа.  Можно создать метод, выполняющий нужное действие с элементом, создать экземпляр делегата <xref:System.Action%601> для представления этого метода, а затем передать массив и делегат в статический универсальный метод <xref:System.Array.ForEach%2A?displayProperty=fullName>.  Метод вызывается для каждого элемента массива.  
  
 Универсальный класс <xref:System.Collections.Generic.List%601> также предоставляет метод <xref:System.Collections.Generic.List%601.ForEach%2A>, использующий делегат <xref:System.Action%601>.  Этот метод неуниверсальный.  
  
> [!NOTE]
>  Это интересная особенность универсальных типов и методов.  Метод <xref:System.Array.ForEach%2A?displayProperty=fullName> должен быть статическим \(`Shared` в Visual Basic\) и универсальным, так как <xref:System.Array> не является универсальным типом. Единственной причиной, по которой можно задать тип для <xref:System.Array.ForEach%2A?displayProperty=fullName>, является то, что метод имеет свой собственный список параметров типа.  Напротив, неуниверсальный метод <xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=fullName> принадлежит к универсальному классу <xref:System.Collections.Generic.List%601>, поэтому он просто использует параметр типа своего класса.  Класс является строго типизированным, поэтому этот метод может быть методом экземпляра.  
  
 Универсальный делегат <xref:System.Predicate%601> представляет метод, который определяет, удовлетворяет ли конкретный элемент заданным критериям.  Его можно использовать со следующими статическими универсальными методами <xref:System.Array> для поиска элемента или набора элементов: <xref:System.Array.Exists%2A>, <xref:System.Array.Find%2A>, <xref:System.Array.FindAll%2A>, <xref:System.Array.FindIndex%2A>, <xref:System.Array.FindLast%2A>, <xref:System.Array.FindLastIndex%2A> и <xref:System.Array.TrueForAll%2A>.  
  
 <xref:System.Predicate%601> также работает с соответствующими неуниверсальными методами экземпляра универсального класса <xref:System.Collections.Generic.List%601>.  
  
 Универсальный делегат <xref:System.Comparison%601> позволяет указать порядок сортировки для элементов массива или списка, для которых нет собственного порядка сортировки, или переопределить их собственный порядок сортировки.  Создайте метод, выполняющий сравнение, создайте экземпляр делегата <xref:System.Comparison%601> для представления этого метода, а затем передайте массив и делегат в статический универсальный метод [Array.Sort\<T\>\(T\<xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29?displayProperty=fullName>.  Универсальный класс <xref:System.Collections.Generic.List%601> предоставляет соответствующий перегруженный метод экземпляра <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29?displayProperty=fullName>.  
  
 Универсальный делегат <xref:System.Converter%602> позволяет определить преобразование между двумя типами и преобразовать массив одного типа в массив другого типа \(либо преобразовать список одного типа в список другого типа\).  Создайте метод, преобразующий элементы существующего списка в новый тип, создайте экземпляр делегата, который будет представлять метод, и используйте универсальный статический метод <xref:System.Array.ConvertAll%2A?displayProperty=fullName> для создания массива нового типа из исходного массива или универсальный метод экземпляра <xref:System.Collections.Generic.List%601.ConvertAll%2A?displayProperty=fullName> для создания списка нового типа из исходного списка.  
  
### Связывание делегатов  
 Многие методы, использующие эти делегаты, возвращают массив или список, который можно передать другому методу.  Например, если вы хотите выбрать определенные элементы массива, преобразовать их в новый тип и сохранить в новый массив, вы можете передать массив, возвращенный универсальным методом <xref:System.Array.FindAll%2A>, в универсальный метод <xref:System.Array.ConvertAll%2A>.  Если у нового типа элементов нет естественного порядка сортировки, вы можете передать массив, возвращенный универсальным методом <xref:System.Array.ConvertAll%2A>, в универсальный метод [Sort\<T\>\(T\<xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29>.  
  
## См. также  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [Универсальные шаблоны](../../../docs/standard/generics/index.md)   
 [Универсальные коллекции в .NET Framework](../../../docs/standard/generics/collections.md)   
 [Универсальные интерфейсы](../../../docs/standard/generics/interfaces.md)   
 [Ковариация и контрвариация](../../../docs/standard/generics/covariance-and-contravariance.md)