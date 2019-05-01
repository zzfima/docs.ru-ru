---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009842"
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|3507|  
|Ключевые слова|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает, что конечная точка службы была добавлена.  
  
## <a name="message"></a>Сообщение  
 Конечная точка службы была добавлена для адреса «%1», привязки «%2» и контракта «%3».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Адрес|xs:string|Адрес конечной точки.|  
|Привязка|xs:string|Привязка конечной точки.|  
|Контракт|xs:string|Контракт конечной точки.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
