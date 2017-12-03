---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b86289340c35d24552b1d524a3cceaacb2f0420
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|3503|  
|Ключевые слова|WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает, что обнаружен повторяющийся запрос CorrelationQuery. Повторяющийся запрос не будет использоваться при расчете корреляции.  
  
## <a name="message"></a>Сообщение  
 Обнаружен повторяющийся запрос CorrelationQuery с параметром Where=«%1». Это дубликат не будет использоваться при расчете корреляции.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Where|xs:string|Часть Where в запросе корреляции.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
