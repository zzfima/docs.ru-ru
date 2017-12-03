---
title: "Ресурсы операционной системы, необходимые WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31006331f5e8a71bf3f4fb9a68c31cb32d0b6f2b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="operating-system-resources-required-by-wcf"></a>Ресурсы операционной системы, необходимые WCF
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] зависит о нескольких ресурсов, работа которых обеспечивается операционной системой. В следующей таблице перечислены эти ресурсы.  
  
|Ресурс|Описание|  
|--------------|-----------------|  
|Координатор распределенных транзакций (Майкрософт)|Требуется для поддержки транзакций OleTx.|  
|службы IIS|Требуется, если необходимо использовать службы IIS для размещения приложения.|  
|Служба активации Windows (WAS)|Требуется, если необходимо использовать WAS для размещения приложения.|  
  
## <a name="see-also"></a>См. также  
 [Требования к системе](../../../docs/framework/wcf/wcf-system-requirements.md)
