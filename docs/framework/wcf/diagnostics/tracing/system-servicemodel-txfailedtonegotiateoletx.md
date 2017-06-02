---
title: "System.ServiceModel.TxFailedToNegotiateOleTx | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.TxFailedToNegotiateOleTx
Согласование протокола OleTransactions невозможно завершить для заданного контекста координации.  
  
## Описание  
 Трассируется, если входящая транзакция с информацией OleTx не может использовать прикрепленную информацию OleTx и вместо этого использует WS\-AT.  
  
## Устранение неполадок  
 Показывает возможную проблему обмена данными MSDTC RPC между компьютерами.Появление большого количества таких трассировок в журнале может привести к значительному снижению производительности.Если информация OleTx не требуется, установите `OleTxUpgradeEnabled` на значение 0 в конфигурации реестра WS\-AT.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)