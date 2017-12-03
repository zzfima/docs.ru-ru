---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5750748f2885418b8992ce54bbdf6a92b8e1fe39
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="219---serviceexception"></a>219 - ServiceException
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|219|  
|Ключевые слова|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается при обнаружении службой WCF необработанного исключения. В число необработанных входят исключения, возникшие во время активации, обработки сообщений и выполнения пользовательского кода.  
  
## <a name="message"></a>Сообщение  
 Во время обработки сообщения возникло необработанное исключение типа «%2». Полное исключение ToString: %1.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|Результат вызова метода `ToString`() относительно исключения CLR.|  
|ExceptionTypeName|`xs:string`|Имя CLR FullName типа исключения.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
