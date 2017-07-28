---
title: "Разработка с обеспечением расширяемости | Microsoft Docs"
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
  - "расширение библиотек классов"
  - "расширяемость с помощью библиотек классов в .NET Framework"
  - "Класс рекомендации по разработке библиотек [платформа .NET Framework] расширяемости"
  - "расширяемость библиотеки классов [платформа .NET Framework]"
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Разработка с обеспечением расширяемости
Важным аспектом разработки платформу убедиться, что внимательно учитывать расширяемость платформы. Это требует понимания затраты и преимущества, связанные с различных механизмов расширения. В этой главе помогает решить, какие механизмы расширения — подклассы событий, виртуальные члены, обратные вызовы и т. д, соответствуют требованиям вашей платформы.  
  
 Для обеспечения расширяемости в платформ разными способами. Они в диапазоне от менее мощные, но менее затратным до очень мощный, но дорого. Для любого данного расширения требования следует выбрать бы дорогостоящим механизмом расширения, соответствующий требованиям. Имейте в виду, что обычно возможно позже добавить дополнительные расширения, но никогда не позволит немедленно без критических изменений.  
  
## В этом подразделе  
 [Незапечатанные классы](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Защищенные члены](../../../docs/standard/design-guidelines/protected-members.md)  
 [События и обратные вызовы](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Виртуальные члены](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Абстракции \(абстрактные типы и интерфейсы\)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Базовые классы для реализации абстракций](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Запечатывание](../../../docs/standard/design-guidelines/sealing.md)  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)