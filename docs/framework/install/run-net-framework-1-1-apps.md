---
title: "Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework 1.1, выполнение в Windows 8"
  - "Windows 8, выполнение приложений .NET Framework 1.1"
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10
Платформа .NET Framework 1.1 не поддерживается в операционных системах [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10.  В некоторых случаях явно указывается, что для работы приложения требуется именно .NET Framework 1.1.  Тогда следует обратиться к независимому поставщику программного обеспечения, чтобы получить обновленную версию приложения на базе [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] или более поздней версии.  Дополнительные сведения см. в разделе [Миграция с платформы .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).  
  
## Установка .NET Framework 1.1 с компакт\-диска или из Центра загрузки  
 Платформу .NET Framework 1.1 невозможно установить вручную в [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10.  Оно более не поддерживается.  При попытке установить пакет отображается следующее сообщение об ошибке: "Невозможно продолжить установку, поскольку эта версия .NET Framework несовместима с ранее установленной версией". Для устранения этой проблемы установите [.NET Framework 3.5 с пакетом обновления 1 \(SP1\)](http://www.microsoft.com/download/details.aspx?id=22).  Эта версия включает платформу .NET Framework 2.0 \(выпуск, следующий за выпуском .NET Framework 1.1\), поддерживаемую в [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] и Windows 10.  Рекомендуется сперва пробовать установить приложение — возможно, оно обновится автоматически и будет использовать последнюю версию платформы .NET Framework.  Если этого не произойдет, обратитесь к независимому поставщику программного обеспечения за обновленной версией.  
  
## См. также  
 [Миграция с платформы .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [Установка платформы .NET Framework 3.5 в Windows 8 и более поздних версий](../../../docs/framework/install/net-framework-3-5-on-windows-8-plus.md)