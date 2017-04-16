---
title: "System.ServiceModel.TxCompletionStatusCompletedForError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.TxCompletionStatusCompletedForError
Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.  
  
## Описание  
 Трассируется, если при попытке завершить текущую транзакцию возникает ошибка.Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.  
  
## Устранение неполадок  
 Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие\-либо действия.  
  
## См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)