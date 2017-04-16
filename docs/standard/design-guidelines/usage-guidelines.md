---
title: "Правила использования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Класс рекомендации по разработке библиотек [платформа .NET Framework] рекомендации по использованию"
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Правила использования
Этот раздел содержит рекомендации по использованию общих типов в общедоступном API. Дело с прямого использования встроенных типов \(например, атрибуты сериализации\) и Framework перегрузка общих операторов.  
  
 <xref:System.IDisposable?displayProperty=fullName> Интерфейс не рассматривается в этом разделе, но рассматривается в [Шаблон удаления](../../../docs/standard/design-guidelines/dispose-pattern.md) разделе.  
  
> [!NOTE]
>  Инструкции и Дополнительные сведения о других типичных встроенных типов .NET Framework, см в следующих разделах справки: <xref:System.DateTime?displayProperty=fullName>, <xref:System.DateTimeOffset?displayProperty=fullName>, <xref:System.ICloneable?displayProperty=fullName>, <xref:System.IComparable%601?displayProperty=fullName>, <xref:System.IEquatable%601?displayProperty=fullName>, <xref:System.Nullable%601?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, <xref:System.Uri?displayProperty=fullName>.  
  
## В этом подразделе  
 [Массивы](../../../docs/standard/design-guidelines/arrays.md)  
 [Атрибуты](../../../docs/standard/design-guidelines/атрибуты.md)  
 [Коллекции](../../../amples/snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/collections.vcxproj)  
 [Сериализация](../../../docs/standard/design-guidelines/сериализация.md)  
 [Использование System.Xml](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [Операторы равенства](../../../docs/standard/design-guidelines/equality-operators.md)  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)