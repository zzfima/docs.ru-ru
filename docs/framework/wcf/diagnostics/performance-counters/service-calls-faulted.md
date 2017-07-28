---
title: "Служба: сбои вызовов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Служба: сбои вызовов
Имя счетчика: Calls Faulted  
  
## Описание  
 Количество вызовов данной службы, которые возвратили сообщение о сбое.В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы службы передают информацию об ошибке обработки с помощью сообщений о сбоях протокола SOAP.Сообщения об ошибках SOAP — это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.  
  
## См. также  
 [Задание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)