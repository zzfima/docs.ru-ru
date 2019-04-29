---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781645"
---
# <a name="222---operationfailed"></a>222 - OperationFailed
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|222|  
|Ключевые слова|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается в том случае, когда `OperationInvoker` модели службы по умолчанию обнаруживает исключение при вызове его метода. Обратите внимание, что исключения, производные от `FaultException`, не вызывают это событие.  
  
## <a name="message"></a>Сообщение  
 Метод «%1» вызвал необработанное исключение после того, как был вызван OperationInvoker. Длительность вызова метода составила «%2» мс.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Имя метода|`xs:string`|Имя CLR метода, который был вызван `OperationInvoker`.|  
|Длительность|`xs:long`|Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName". Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
