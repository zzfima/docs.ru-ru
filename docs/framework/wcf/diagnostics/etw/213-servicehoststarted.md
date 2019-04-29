---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781827"
---
# <a name="213---servicehoststarted"></a>213 - ServiceHostStarted
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|213|  
|Ключевые слова|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost|  
|Уровень|LogAlways|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается при запуске службы, размещенной на веб-сервере. Обычно это происходит, когда служба активируется сообщением. Это также может произойти, если служба настроена для автоматического запуска.  
  
## <a name="message"></a>Сообщение  
 ServiceHost запущена: «%1».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Имя типа службы|`xs:string`|Имя CLR FullName типа реализации службы.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии. Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName". Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
