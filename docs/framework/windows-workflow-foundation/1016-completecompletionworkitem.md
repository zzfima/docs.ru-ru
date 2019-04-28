---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925090"
---
# <a name="1016---completecompletionworkitem"></a>1016 - CompleteCompletionWorkItem
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1016|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает на завершение CompletionWorkItem.  
  
## <a name="message"></a>Сообщение  
 CompletionWorkItem завершен для родительского действия «%1», DisplayName «%2», InstanceId «%3». Завершено действие «%4», DisplayName «%5», InstanceId «%6».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Имя типа родительского действия.|  
|ParentDisplayName|xs:string|Отображаемое имя родительского действия.|  
|ParentInstanceId|xs:string|Идентификатор экземпляра родительского действия.|  
|CompletedActivity|xs:string|Имя типа завершенного действия.|  
|CompletedActivityDisplayName|xs:string|Отображаемое имя завершенного действия.|  
|CompletedActivityInstanceId|xs:string|Идентификатор экземпляра завершенного действия.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
