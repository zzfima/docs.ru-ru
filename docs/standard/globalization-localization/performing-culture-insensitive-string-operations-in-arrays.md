---
title: "Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров | Microsoft Docs"
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
  - "массивы [платформа .NET Framework], операции со строками без учета языка и региональных параметров"
  - "comparer - параметр"
  - "операции со строками без учета языка и региональных параметров, в массивах"
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров
Перегрузки методов <xref:System.Array.Sort%2A?displayProperty=fullName> и <xref:System.Array.BinarySearch%2A?displayProperty=fullName> выполняют сортировку с учетом языка и региона, используя свойство <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName>.  Результат, возвращаемый этими методами, зависит от языка и региона и может различаться в различных средах из\-за различий в порядках сортировки.  Чтобы результат не зависел от языка и региональных параметров, используйте одну из перегрузок этого метода, которая принимает параметр `comparer`.  Параметр `comparer` указывает реализацию интерфейса <xref:System.Collections.IComparer>, используемую при сравнении элементов в массиве.  Для параметра необходимо определить настраиваемый инвариантный класс сравнения, использующий свойство <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  Пример настраиваемого инвариантного класса сравнения приведен в подразделе "Использование класса SortedList" раздела [Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).  
  
 **Примечание**. При передаче методу сравнения свойства **CultureInfo.InvariantCulture** сравнение выполняется без учета языка и региональных параметров.  Однако это не приводит к нелингвистическому сравнению, например для путей к файлам, разделов реестра и переменных среды.  Кроме того, при этом не поддерживается принятие решений системы безопасности на основе результатов сравнения.  Для выполнения нелингвистического сравнения и принятия решений системы безопасности на основе результатов сравнения необходимо использовать метод сравнения, принимающий значение <xref:System.StringComparison>.  В этом случае приложение должно передавать значение <xref:System.StringComparison>.  
  
## См. также  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 <xref:System.Array.BinarySearch%2A?displayProperty=fullName>   
 <xref:System.Collections.IComparer>   
 [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)