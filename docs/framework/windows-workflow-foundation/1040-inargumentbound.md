---
title: 1040 - InArgumentBound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49d00691b25ebc02d4b32e076a4563f846f13cbe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1040---inargumentbound"></a>1040 - InArgumentBound
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1040|  
|Ключевые слова|WFActivities|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, для аргумента In выполнена привязка.  
  
## <a name="message"></a>Сообщение  
 В аргументе «%1» действия «%2», DisplayName «%3», InstanceId «%4» были связаны со значением %5.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InArgument|xs:string|Имя аргумента InArgument.|  
|Действие|xs:string|Имя типа действия.|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|InstanceId|xs:string|Идентификатор экземпляра действия.|  
|Значение|xs:string|Значение, привязанное к аргументу InArgument.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
