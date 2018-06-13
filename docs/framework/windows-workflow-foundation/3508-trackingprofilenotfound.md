---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512188"
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|3508|  
|Ключевые слова|WFServices|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.  
  
## <a name="message"></a>Сообщение  
 Не найден TrackingProfile «%1» для ActivityDefinitionId «%2». Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|Имя профиля отслеживания.|  
|ActivityDefinitionId|xs:string|Идентификатор определения действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
