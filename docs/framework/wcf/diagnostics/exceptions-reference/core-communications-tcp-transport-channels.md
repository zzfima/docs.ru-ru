---
title: "Основное взаимодействие: транспортные каналы TCP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Основное взаимодействие: транспортные каналы TCP
В этом разделе перечислены все исключения, вызываемые каналами транспорта TCP.  
  
## Список исключений  
  
|Код ресурса|Строка ресурса|  
|-----------------|--------------------|  
|SocketCloseReadTimeout|Удаленная конечная точка заданного сокета не ответила на запрос на закрытие в течение заданного выделенного времени ожидания.  Возможно, удаленная конечная точка не вызывает метод Close после получения сигнала конца файла \(null\) от операции Receive.  Возможно, выделенное для этой операции время было частью более длительного времени ожидания.|