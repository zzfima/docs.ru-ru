---
title: "Универсальные интерфейсы | Microsoft Docs"
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
  - "сравнения на равенство [платформа .NET Framework]"
  - "универсальные интерфейсы [платформа .NET Framework]"
  - "универсальные шаблоны [платформа .NET Framework], интерфейсы"
  - "сравнения на упорядоченность [платформа .NET Framework]"
ms.assetid: 88bf5b04-d371-4edb-ba38-01ec7cabaacf
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Универсальные интерфейсы
В этом разделе приводится обзор универсальных интерфейсов, которые предоставляют общие функциональные возможности для различных семейств универсальных типов.  
  
## Универсальные интерфейсы  
 Универсальные интерфейсы — это типобезопасные аналоги неуниверсальных интерфейсов, предназначенные для сортировки и сравнения на равенство, а также для реализации функциональности, совместно используемой универсальными коллекциями.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] параметры типов нескольких универсальных интерфейсов помечены как ковариантные или контравариантные, что обеспечивает дополнительную гибкость при назначении и использовании типов, реализующих эти интерфейсы.  См. раздел [Ковариация и контрвариация](../../../docs/standard/generics/covariance-and-contravariance.md).  
  
### Упорядочение и сравнение на равенство  
 В пространстве имен <xref:System> универсальные интерфейсы <xref:System.IComparable%601?displayProperty=fullName> и <xref:System.IEquatable%601?displayProperty=fullName>, как и их неуниверсальные аналоги, определяют методы для упорядочения и сравнения на равенство соответственно.  Типы реализуют эти интерфейсы для предоставления возможности выполнения таких сравнений.  
  
 В пространстве имен <xref:System.Collections.Generic> универсальные интерфейсы <xref:System.Collections.Generic.IComparer%601> и <xref:System.Collections.Generic.IEqualityComparer%601> позволяют определить операции упорядочения или сравнения на равенство для типов, которые не реализуют универсальный интерфейс <xref:System.IComparable%601?displayProperty=fullName> или <xref:System.IEquatable%601?displayProperty=fullName>. Кроме того, они позволяют переопределить эти отношения для типов, реализующих эти интерфейсы.  Эти интерфейсы используются методами и конструкторами многих универсальных классов коллекций.  Например, можно передать универсальный объект <xref:System.Collections.Generic.IComparer%601> в конструктор класса <xref:System.Collections.Generic.SortedDictionary%602>, чтобы указать порядок сортировки для типа, который не реализует универсальный интерфейс <xref:System.IComparable%601?displayProperty=fullName>.  Предусмотрены перегрузки универсального статического метода <xref:System.Array.Sort%2A?displayProperty=fullName> и метода экземпляра <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> для сортировки массивов и списков с помощью реализаций универсального интерфейса <xref:System.Collections.Generic.IComparer%601>.  
  
 Универсальные классы <xref:System.Collections.Generic.Comparer%601> и <xref:System.Collections.Generic.EqualityComparer%601> предоставляют базовые классы для реализаций универсальных интерфейсов <xref:System.Collections.Generic.IComparer%601> и <xref:System.Collections.Generic.IEqualityComparer%601>. Кроме того, они предоставляют операции упорядочения и сравнения на равенство по умолчанию через соответствующие свойства <xref:System.Collections.Generic.Comparer%601.Default%2A?displayProperty=fullName> и <xref:System.Collections.Generic.EqualityComparer%601.Default%2A?displayProperty=fullName>.  
  
### Функциональные возможности коллекций  
 Универсальный интерфейс <xref:System.Collections.Generic.ICollection%601> представляет собой базовый интерфейс для универсальных типов коллекций.  Он предоставляет базовые функции для добавления, удаления, копирования и перечисления элементов.  <xref:System.Collections.Generic.ICollection%601> наследуется от универсального интерфейса <xref:System.Collections.Generic.IEnumerable%601> и неуниверсального интерфейса <xref:System.Collections.IEnumerable>.  
  
 Универсальный интерфейс <xref:System.Collections.Generic.IList%601> расширяет универсальный интерфейс <xref:System.Collections.Generic.ICollection%601> с помощью методов для получения элементов по индексу.  
  
 Универсальный интерфейс <xref:System.Collections.Generic.IDictionary%602> расширяет универсальный интерфейс <xref:System.Collections.Generic.ICollection%601> с помощью методов для получения элементов по ключу.  Универсальные типы словарей в библиотеке базовых классов .NET Framework также реализуют неуниверсальный интерфейс <xref:System.Collections.IDictionary>.  
  
 Универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601> предоставляет структуру универсального перечислителя.  Универсальный интерфейс <xref:System.Collections.Generic.IEnumerator%601>, реализуемый универсальными перечислителями, наследуется от неуниверсального интерфейса <xref:System.Collections.IEnumerator>. Члены <xref:System.Collections.IEnumerator.MoveNext%2A> и <xref:System.Collections.IEnumerator.Reset%2A>, которые не зависят от параметра типа `T`, присутствуют только в неуниверсальном интерфейсе.  Это означает, что любой потребитель неуниверсального интерфейса также может использовать универсальный интерфейс.  
  
## См. также  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [Универсальные шаблоны](../../../docs/standard/generics/index.md)   
 [Универсальные коллекции в .NET Framework](../../../docs/standard/generics/collections.md)   
 [Универсальные делегаты для управления массивами и списками](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)   
 [Ковариация и контрвариация](../../../docs/standard/generics/covariance-and-contravariance.md)