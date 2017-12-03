---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abe1f560cc984551f069a75873a7e5545aec03cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="4212---lockretrytimeout"></a>4212 - LockRetryTimeout
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|4212|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.  
  
## <a name="message"></a>Сообщение  
 Время ожидания при попытке получить блокировку для экземпляра.  Не удалось выполнить операцию за выделенное время ожидания %1. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Delay|xs:string|Задержка между попытками.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
