---
title: "System.ServiceModel.Channels.HttpChannelMessageReceiveFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Сбой получения сообщения по каналу HTTP.  
  
## Описание  
 Данная трассировка может выдаваться в качестве предупреждения или ошибки.В обоих случаях трассировка выдается, если при входящем HTTP\-запросе не найден совместимый прослушиватель и HTTP\-запрос получил отказ.Это может произойти по той причине, что HTTP\-команда запроса не была распознана прослушивателем HTTP, либо потому что прослушиватель ожидал передачи данных по адресу, на который был направлен запрос.Данная трассировка выдается как предупреждение при независимом размещении и как ошибка при размещении службы в IIS.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)