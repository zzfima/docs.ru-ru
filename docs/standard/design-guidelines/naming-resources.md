---
title: "Именование ресурсов | Microsoft Docs"
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
  - "ресурсы, локализованные имена [платформа .NET Framework]"
  - "локализация, правила именования"
  - "имена ресурсов"
  - "глобальные приложения, правила именования"
  - "приложения на разных языках, правила именования"
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Именование ресурсов
Поскольку локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойства, правилам именования для ресурсов похожи на правила свойств.  
  
 **✓ сделать** использовать PascalCasing в ключах ресурсов.  
  
 **✓ сделать** предоставить описательные, а не короткие идентификаторы.  
  
 **X не** использовать зарезервированные слова языка основных языков среды CLR.  
  
 **✓ сделать** использовать только буквы, цифры и символы подчеркивания в именовании ресурсов.  
  
 **✓ сделать** использовать следующее соглашение об именовании для ресурсов сообщение исключения.  
  
 Идентификатор ресурса должен быть именем типа исключения, а также с коротким идентификатором исключения:  
  
 `ArgumentExceptionIllegalCharacters`   
 `ArgumentExceptionInvalidName`   
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)   
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)