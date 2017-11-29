---
title: 441 - StopSignpostEvent1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e6c5a3b31378347b6e3880361cd99d3f6851b686
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="441--stopsignpostevent1"></a>441 - StopSignpostEvent1
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|441|  
|Ключевые слова|Устранение неполадок|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 В трассировке действий указывает на то, что сообщение закончило пересекать границу действия при отправке или приеме.  
  
## <a name="message"></a>Сообщение  
 Граница действия.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
