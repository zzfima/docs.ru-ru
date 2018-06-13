---
title: 404 - ResumeSignpostEvent
ms.date: 03/30/2017
ms.assetid: 395cc7ca-f35f-4295-be97-39a077f99c97
ms.openlocfilehash: 258e2f7e4b9dc1025461519593204c196bf6f415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33467475"
---
# <a name="404---resumesignpostevent"></a>404 - ResumeSignpostEvent
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|404|  
|Ключевые слова|Устранение неполадок|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие отмечает продолжение сквозного действия. В ней содержится имя действия.  
  
## <a name="message"></a>Сообщение  
 Граница действия.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
