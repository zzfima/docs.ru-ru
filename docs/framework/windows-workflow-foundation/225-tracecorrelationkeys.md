---
title: 225 - TraceCorrelationKeys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a1f74ebfef7a2582f3eb25c3571cd05c4518ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|225|  
|Ключевые слова|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается, если в качестве службы рабочего процесса используется корреляция на основе содержимого. Оно содержит ключи, применяемые для корреляции сообщения с экземпляром.  
  
## <a name="message"></a>Сообщение  
 Вычисленный ключ корреляции «%1» с использованием значений «%2» в родительской области «%3».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Instance Key|`xs:GUID`|Ключ, созданный из значений корреляции.|  
|Значения|`xs:string`|Значения, использованные для вычисления ключа экземпляра корреляции.|  
|Parent Scope|`xs:string`||  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
