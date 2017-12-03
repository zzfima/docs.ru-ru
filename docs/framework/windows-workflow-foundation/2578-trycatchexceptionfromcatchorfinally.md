---
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ab39fbc05c4661dd5af37297540eafd67990eb58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a>2578 - TryCatchExceptionFromCatchOrFinally
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|2578|  
|Ключевые слова|WFActivities|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действие Catch или Finally вызвало исключение.  
  
## <a name="message"></a>Сообщение  
 В действии Catch или Finally, связанном с действием TryCatch «%1», произошло исключение.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|Отображаемое имя действия.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
