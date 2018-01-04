---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb6af10c45e7a93e9a68e6150e5d239002cce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1022---startbookmarkworkitem"></a>1022 - StartBookmarkWorkItem
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1022|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что начинается выполнение BookmarkWorkItem.  
  
## <a name="message"></a>Сообщение  
 Начинается выполнение элемента bookmarkworkitem для элемента Activity «%1», DisplayName: «%2», InstanceId: «%3».  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|BookmarkName|xs:string|Имя закладки.|  
|BookmarkScope|xs:string|Область закладки.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
