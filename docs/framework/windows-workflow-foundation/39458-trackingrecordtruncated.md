---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774417"
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|39458|  
|Ключевые слова|WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что запись отслеживания была усечена. Данные переменных, заметок, пользователей удалены.  
  
## <a name="message"></a>Сообщение  
 Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2. Данные переменных, заметок, пользователей удалены  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Номер записи отслеживания.|  
|ProviderId|xs:string|Идентификатор поставщика трассировки событий Windows.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
