---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1035|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действие задало транзакцию среды выполнения.  
  
## <a name="message"></a>Сообщение  
 Транзакция среды выполнения задана элементом действия «%1», DisplayName: «%2», InstanceId: «%3».  Выполнение изолировано в элементе Activity «%4», DisplayName: «%5», InstanceId: '%6'.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|IsolatedActivity|xs:string|Имя типа для действия, в котором изолирована транзакция.|  
|IsolatedActivityDisplayName|xs:string|Имя отображаемого имени действия, в котором изолирована транзакция.|  
|IsolatedActivityInstanceId|xs:string|Идентификатор экземпляра действия, в котором изолирована транзакция.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
