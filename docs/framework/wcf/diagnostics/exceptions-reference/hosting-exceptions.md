---
title: "Исключения размещения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Исключения размещения
В этом разделе перечислены все исключения, создаваемые Hosting.  
  
## Список исключений  
  
|Код ресурса|Строка ресурса|  
|-----------------|--------------------|  
|Hosting\_AddressIsAbsoluteUri|Полный универсальный код ресурса \(URI\) не допускается.Интерфейс API ServiceHostingEnvironment.EnsureServiceAvailable не допускает использования полных URI.Используйте виртуальный путь для соответствующей службы.|  
|Hosting\_BuildProviderCouldNotCreateType|Не удалось загрузить указанный тип CLR во время компиляции службы.Убедитесь, что этот тип определен в исходном файле, расположенном в каталоге \\\\App\_Code приложения, содержится в скомпилированной сборке, расположенной в каталоге \\\\bin приложения, или присутствует в сборке, установленной в глобальном кэше сборок.Имя типа вводится с учетом регистра.Некоторые каталоги, такие как \\\\App\_Code и \\\\bin, должны располагаться в корневом каталоге приложения.Каталоги \\\\App\_Code and \\\\bin не могут быть вложены в подкаталоги.|