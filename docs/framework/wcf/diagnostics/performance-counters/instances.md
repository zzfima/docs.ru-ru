---
title: "Экземпляры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ed0c4a6f13ddcafdb3a9a773be9cd3f017474ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="instances"></a>Экземпляры
Имя счетчика: Instances.  
  
## <a name="description"></a>Описание  
 Число контекстов экземпляра, которое в настоящий момент содержит служба.  
  
 В большинстве случаев число контекстов экземпляра идентично числу экземпляров. Однако приведенные ниже сценарии являются исключением из этого правила.  
  
-   Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.  
  
-   <xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
