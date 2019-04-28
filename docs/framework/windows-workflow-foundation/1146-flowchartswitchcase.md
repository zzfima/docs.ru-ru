---
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: 9f4e3af664ed30634e4b56f16cd6caf2366c3674
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923907"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1146|  
|Ключевые слова|WFActivities|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, какой вариант (Case) был выбран в параметре блок-схемы.  
  
## <a name="message"></a>Сообщение  
 Блок-схема «%1»/FlowSwitch: выбран вариант Case «%2».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Блок-схема|xs:string|Отображаемое имя блок-схемы.|  
|Case|xs:string|Выбранный вариант Case.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
