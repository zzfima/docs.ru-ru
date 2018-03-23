---
title: 302 - UserDefinedWarningOccurred
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae455c9eec2335fcf6eb5473932bd8d9e5d2db95
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2018
---
# <a name="302---userdefinedwarningoccurred"></a>302 - UserDefinedWarningOccurred
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|302|  
|Ключевые слова|Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается в пользовательском коде. Разработчики могут создать это событие, если определенное пользователем событие предупреждения возникло в принадлежащей им службе. Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>. Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.  
  
## <a name="message"></a>Сообщение  
 Имя: «%1», ссылка: «%2», полезные данные: %3  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|name|`xs:string`|Определенное пользователем имя события.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы". Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Payload|`xs:string`|Определенные пользователем полезные данные события.|
