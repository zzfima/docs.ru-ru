---
title: "Основное взаимодействие: поддержка Webhost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Основное взаимодействие: поддержка Webhost
В этом разделе перечислены все исключения, вызываемые средствами поддержки Webhost.  
  
## Список исключений  
  
|Код ресурса|Строка ресурса|  
|-----------------|--------------------|  
|Hosting\_CompatibilityServiceNotHosted|Эта служба требует совместимости с ASP.NET.Она должна также быть размещена в IIS.Либо разместите службу в IIS с включенной совместимостью с ASP.NET в файле Web.config, либо задайте для свойства AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode значение, отличное от "Required".|  
|Hosting\_ListenerNotFoundForActivationInRecycling|В настоящее время ни один канал не ожидает передачу данных на заданном адресе.Если приложение перезапускается, служба закрывается.|  
|Hosting\_NonHTTPInCompatibilityMode|При совместимости с ASP.NET поддерживаются только протоколы HTTP и HTTPS.Удалите указанную конечную точку или отключите совместимость с ASP.NET для приложения.|  
|Hosting\_ProcessNotExecutingUnderHostedContext|Указанный процесс размещения невозможно вызвать в текущей среде размещения.Этот API требует, чтобы вызывающее приложение было размещено в службах IIS или в службе активации Windows.|  
|Hosting\_ServiceCompatibilityRequire|Активировать службу невозможно, поскольку она требует совместимости с ASP.NET.Совместимость с ASP.NET для этого приложения не включена.Либо включите совместимость с ASP.NET в файле Web.config, либо установите AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|