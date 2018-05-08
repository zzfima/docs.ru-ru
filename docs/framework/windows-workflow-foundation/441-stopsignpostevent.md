---
title: 441 - StopSignpostEvent1
ms.date: 03/30/2017
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
ms.openlocfilehash: 69430372a472b19caaa9f1de9c0f06886001353e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
