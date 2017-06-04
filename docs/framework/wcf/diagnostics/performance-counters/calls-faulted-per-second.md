---
title: "Количество сбоев вызовов в секунду | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Количество сбоев вызовов в секунду
Имя счетчика: Calls Faulted Per Second  
  
## Описание  
 Число вызовов, возвращающих ошибки этой операции за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по приведенной ниже формуле.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)  
  
 В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.Сообщения об ошибках SOAP — это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.  
  
## См. также  
 [Задание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)