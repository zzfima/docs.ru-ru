---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06d4695eb125475f41a94c7f2266df6d2c3f400d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4203---renewlocksystemerror"></a>4203 - RenewLockSystemError
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|4203|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален. SqlWorkflowInstanceStore будет прервано.  
  
## <a name="message"></a>Сообщение  
 Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален. Прерывание блокировки SqlWorkflowInstanceStore.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
