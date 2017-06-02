---
title: "Руководство по миграции на .NET Framework&#160;4.6 и 4.5  | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, перенос приложений на"
  - "миграция, .NET Framework"
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Руководство по миграции на .NET Framework&#160;4.6 и 4.5 
Если приложение создано с использованием более ранней версии платформы .NET Framework, обычно можно легко обновить его до .NET Framework 4.5, 4.5.1 или 4.6. Откройте проект в Visual Studio. Если проект был создан в более ранней версии, автоматически откроется диалоговое окно **Совместимость проекта**. Дополнительные сведения об обновлении проектов в Visual Studio 2013 см. в разделах [Практическое руководство. Обновление проектов, созданных в более ранних версиях Visual Studio](http://msdn.microsoft.com/library/vstudio/ms185327\(v=vs.100\).aspx) и [Перенос, миграция и обновление проектов Visual Studio](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md).  
  
 Однако некоторые изменения в платформе .NET Framework требуют внесения изменений в код. Кроме того, возможно, вы захотите воспользоваться преимуществами новых возможностей в версии .NET Framework 4.5, ее доработанных выпусках или платформе Framework 4.6. Внесение подобных изменений в приложение для новой версии платформы .NET Framework обычно называется *миграцией*. Если нет необходимости в миграции приложения, его можно выполнить в среде .NET Framework 4.5 и более поздних версий без компиляции.  
  
## Ресурсы миграции  
 Перед миграцией приложения из более ранних версий .NET Framework в версию 4.5, 4.5.1 или 4.5.2 просмотрите следующие документы:  
  
-   См. [Версии и зависимости](../../../docs/framework/migration-guide/versions-and-dependencies.md), чтобы определить версию среды CLR, лежащую в основе каждой версии .NET Framework, и ознакомиться с рекомендациями по определению целевой платформы для приложений.  
  
-   Просмотрите [Совместимость приложений](../../../docs/framework/migration-guide/application-compatibility.md), чтобы узнать об изменениях в среде выполнения и изменении целевой платформы, которые могут повлиять на приложение, а также о том, что с ними делать.  
  
-   Просмотрите раздел [Устаревшие классы библиотеки классов](../../../docs/framework/whats-new/whats-obsolete.md), чтобы определить устаревшие типы и члены в коде и рекомендуемые альтернативы.  
  
-   См. [Новые возможности](../../../docs/framework/whats-new/index.md), чтобы узнать о новых возможностях, которые вы, возможно, захотите добавить в приложение.  
  
## См. также  
 [Совместимость приложений в платформе 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Совместимость приложений в платформе 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Миграция с платформы .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [Совместимость версий](../../../docs/framework/migration-guide/version-compatibility.md)   
 [Версии и зависимости](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Практическое руководство. Настройка приложения для поддержки платформы .NET Framework 4 или 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [Новые возможности](../../../docs/framework/whats-new/index.md)   
 [Устаревшие классы библиотеки классов](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Сведения о версиях и сборках платформы .NET Framework](http://go.microsoft.com/fwlink/?LinkId=201701)   
 [Политика жизненного цикла поддержки Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=196607)