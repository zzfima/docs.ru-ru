---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774274"
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 - TimeoutOpeningSqlConnection
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4209|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Error|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что при попытке открыть соединение SQL превышено время ожидания.  
  
## <a name="message"></a>Сообщение  
 Истекло время ожидания при открытии соединения SQL. Не удалось выполнить операцию за выделенное время ожидания %1. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Время ожидания|xs:string|Значение времени ожидания для открытия соединения SQL.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
