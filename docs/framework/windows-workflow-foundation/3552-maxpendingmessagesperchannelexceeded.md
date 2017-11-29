---
title: "3552 – MaxPendingMessagesPerChannelExceeded"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ba5e4aa8e1338321838e40db7d976107315ef64
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 – MaxPendingMessagesPerChannelExceeded
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|3552|  
|Ключевые слова|Quota, WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».  
  
## <a name="message"></a>Сообщение  
 Был достигнут предел регулирования «MaxPendingMessagesPerChannel» «% 1». Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Limit|xs:string|Был достигнут предел регулирования «MaxPendingMessagesPerChannel».|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
