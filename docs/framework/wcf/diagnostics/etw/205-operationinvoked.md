---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7385d34ac2ed0357e964e992a88f96a6a89b1a26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|205|  
|Ключевые слова|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание:  
 Это событие создается непосредственно перед тем, как `OperationInvoker` по умолчанию модели службы начнет вызов метода.  
  
## <a name="message"></a>Сообщение  
 OperationInvoker вызвал метод «%1». Сведения о вызывающем объекте: «%2».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание:|  
|--------------------|--------------------|-----------------|  
|Имя метода|`xs:string`|Имя CLR метода, который был вызван `OperationInvoker`.|  
|Сведения о вызывающем|`xs:string`|IP-адрес и номер порта клиента в формате «IPAddress:PortNumber». Эти два значения извлекаются из свойства сообщения «System.ServiceModel.Channels.RemoteEndpointMessageProperty» в контексте операции. Следует отметить, что для привязок, отличных от TCP, это значение `null`.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
