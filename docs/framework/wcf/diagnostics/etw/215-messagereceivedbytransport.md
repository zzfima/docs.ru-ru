---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: aa1ad30526aa65501e5d9875d3877631ca00879b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964191"
---
# <a name="215---messagereceivedbytransport"></a>215 - MessageReceivedByTransport
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|215|  
|Ключевые слова|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие происходит, когда транспорт на основе TCP получает сообщение. Обратите внимание, что на транспортном уровне для одной операции между клиентом и службой может быть передано несколько сообщений. Это может зависеть от инфраструктуры, и требования безопасности - хороший пример. Следовательно, количество создаваемых событий `MessageReceivedByTransport` может отличаться в зависимости от привязки службы и ее настроек.  
  
> [!NOTE]
> Это событие не создается для односторонних транспортов.  
  
## <a name="message"></a>Сообщение  
 Диспетчер получил сообщение от «%1».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Listen Address|`xs:string`|Адрес, получивший сообщение.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта приложение виртуальный путь&#124;службы&#124;имя_службы". Пример "Default Web site/Калкулатораппликатион&#124;/калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
