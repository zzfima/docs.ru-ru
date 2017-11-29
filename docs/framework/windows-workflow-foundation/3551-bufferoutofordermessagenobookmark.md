---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a380def22c270a3fafe118a426609a93862c447
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 - BufferOutOfOrderMessageNoBookmark
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|3551|  
|Ключевые слова|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает на сбой возобновления закладки. Следующая попытка выполнить операцию получения через буфер будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.  
  
## <a name="message"></a>Сообщение  
 Операция «%2» в экземпляре службы «%1» не может быть выполнена в данный момент. Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Имя операции.|  
|ServiceInstanceId|xs:string|Идентификатор экземпляра службы.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
