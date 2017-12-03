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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5455472a5b9ebdba7aea7d0384ce9cd4a9a2849d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
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
