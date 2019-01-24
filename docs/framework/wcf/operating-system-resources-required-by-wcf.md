---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 759ab099066e300484860cf3f91d6d084ba1d339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527085"
---
# <a name="operating-system-resources-required-by-wcf"></a>Ресурсы операционной системы, необходимые WCF
Windows Communication Foundation (WCF) зависит от нескольких ресурсов, которые предоставляются операционной системой для функции. В следующей таблице перечислены эти ресурсы.  
  
|Ресурс|Описание|  
|--------------|-----------------|  
|Координатор распределенных транзакций (Майкрософт)|Требуется для поддержки транзакций OleTx.|  
|службы IIS|Требуется, если необходимо использовать службы IIS для размещения приложения.|  
|Служба активации Windows (WAS)|Требуется, если необходимо использовать WAS для размещения приложения.|  
  
## <a name="see-also"></a>См. также
- [Требования к системе](../../../docs/framework/wcf/wcf-system-requirements.md)
