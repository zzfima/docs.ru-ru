---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1009|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действие запланировано для выполнения.  
  
## <a name="message"></a>Сообщение  
 Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Имя типа родительского действия.|  
|ParentDisplayName|xs:string|Отображаемое имя родительского действия.|  
|ParentInstanceId|xs:string|Идентификатор экземпляра родительского действия.|  
|ChildActivity|xs:string|Имя типа запланированного дочернего действия.|  
|ChildDisplayName|xs:string|Отображаемое имя запланированного дочернего действия.|  
|ChildInstanceId|xs:string|Идентификатор экземпляра запланированного дочернего действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
