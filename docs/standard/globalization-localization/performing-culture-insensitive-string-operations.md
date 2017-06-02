---
title: "Выполнение строковых операций, не зависящих от языка и региональных параметров | Microsoft Docs"
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
  - "сопоставление регистра"
  - "настраиваемое сопоставление регистра"
  - "язык и региональные параметры, настраиваемые правила сортировки"
  - "настраиваемые правила сортировки"
  - "операции, не зависящие от языка и региональных параметров, для выполнения"
  - "язык и региональные параметры, настраиваемое сопоставление регистра"
  - "операции со строками без учета языка и региональных параметров, перегрузки методов"
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Выполнение строковых операций, не зависящих от языка и региональных параметров
Большинство методов .NET Framework, по умолчанию выполняющих строковые операции с учетом языка и региональных параметров, предоставляет методы перегрузки, позволяющие явно указать используемый язык путем передачи параметра <xref:System.Globalization.CultureInfo>.   Эти перегрузки позволяют устранить языковые и региональные различия, влияющие на правила сортировки и сопоставления регистра, и гарантируют результаты, не зависящие от языковых параметров.  
  
 В этом разделе рассматриваются следующие вопросы о выполнении строковых операции, не зависящих от языковых параметров и региональных параметров, с использованием методов .NET Framework, являющихся по умолчанию зависимыми от языка.  
  
## В этом подразделе  
 [Выполнение сравнения строк без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Описание использования методов <xref:System.String.Compare%2A?displayProperty=fullName> и <xref:System.String.CompareTo%2A?displayProperty=fullName> для сравнения строк без учета языка и региональных параметров.  
  
 [Выполнение смены регистра независимо от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Описание использование методов <xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> и <xref:System.Char.ToLower%2A?displayProperty=fullName> для смены регистра независимо от языка и региональных параметров.  
  
 [Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Описание использования [класса CaseInsensitiveComparer](frlrfSystemCollectionsCaseInsensitiveComparerClassTopic), класса <xref:System.Collections.CaseInsensitiveHashCodeProvider>, [класса SortedList](frlrfSystemCollectionsSortedListClassTopic), [метода ArrayList.Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx) и [метода CollectionsUtil.CreateCaseInsensitiveHashtable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)для выполнения в коллекциях операций, не зависящих от языка и региональных параметров.  
  
 [Выполнение в массивах строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Описание использование методов <xref:System.Array.Sort%2A?displayProperty=fullName> и <xref:System.Array.BinarySearch%2A?displayProperty=fullName> для выполнения в массивах операций без учета языка и региональных параметров.  
  
## Связанные подразделы  
 [Строковые операции, не зависящие от языка и региональных параметров](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Описание причин, по которым необходимо учитывать языковые и региональные параметры при выполнении строковых операции, и указания о том, когда выполнять зависящие от языка операции, а когда — не зависящие.