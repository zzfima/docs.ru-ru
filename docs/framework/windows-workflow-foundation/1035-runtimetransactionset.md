---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924856"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1035|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действие задало транзакцию среды выполнения.  
  
## <a name="message"></a>Сообщение  
 Транзакция среды выполнения установлено с помощью действия «%1», DisplayName: «%2», InstanceId: «%3».  Выполнение изолированного действия «%4», DisplayName: «%5», InstanceId: «%6».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|IsolatedActivity|xs:string|Имя типа для действия, в котором изолирована транзакция.|  
|IsolatedActivityDisplayName|xs:string|Имя отображаемого имени действия, в котором изолирована транзакция.|  
|IsolatedActivityInstanceId|xs:string|Идентификатор экземпляра действия, в котором изолирована транзакция.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
