---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: 8677f25057486247e64879298755fe972bd373d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1023---completebookmarkworkitem"></a>1023 - CompleteBookmarkWorkItem
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1023|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает на завершение BookmarkWorkItem.  
  
## <a name="message"></a>Сообщение  
 BookmarkWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3». BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|BookmarkName|xs:string|Имя закладки.|  
|BookmarkScope|xs:string|Область закладки.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
