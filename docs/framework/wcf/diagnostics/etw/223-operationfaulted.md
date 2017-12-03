---
title: 223 - OperationFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0428d90135823761e7b8a12f560786e34e12734
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="223---operationfaulted"></a>223 - OperationFaulted
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|223|  
|Ключевые слова|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие вызывается в том случае, если при вызове `OperationInvoker` модели службы по умолчанию обнаружено исключение, производное от `FaultException`.  
  
## <a name="message"></a>Сообщение  
 Метод «%1» вызывал исключение FaultException после того, как был вызван OperationInvoker. Длительность вызова метода составила «%2» мс.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|MethodName|`xs:string`|Имя CLR метода, который был вызван `OperationInvoker`.|  
|Длительность|`xs:long`|Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
