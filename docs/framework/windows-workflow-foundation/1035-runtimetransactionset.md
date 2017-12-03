---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
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
