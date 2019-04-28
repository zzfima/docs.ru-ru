---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924661"
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1009|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действие запланировано для выполнения.  
  
## <a name="message"></a>Сообщение  
 Родительское действие «%1» (отображаемое имя «%2», ИД экземпляра «%3») запланировало дочернее действие «%4» (отображаемое имя «%5», ИД экземпляра «%6»).  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Имя типа родительского действия.|  
|ParentDisplayName|xs:string|Отображаемое имя родительского действия.|  
|ParentInstanceId|xs:string|Идентификатор экземпляра родительского действия.|  
|ChildActivity|xs:string|Имя типа запланированного дочернего действия.|  
|ChildDisplayName|xs:string|Отображаемое имя запланированного дочернего действия.|  
|ChildInstanceId|xs:string|Идентификатор экземпляра запланированного дочернего действия.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
