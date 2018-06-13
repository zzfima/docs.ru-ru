---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511271"
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
