---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 4522f1c59c8f74281a0e197338c6206ab29c229b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operating-system-resources-required-by-wcf"></a>Ресурсы операционной системы, необходимые WCF
Windows Communication Foundation (WCF) зависит от нескольких ресурсов, предоставляемых операционной системой для функции. В следующей таблице перечислены эти ресурсы.  
  
|Ресурс|Описание|  
|--------------|-----------------|  
|Координатор распределенных транзакций (Майкрософт)|Требуется для поддержки транзакций OleTx.|  
|службы IIS|Требуется, если необходимо использовать службы IIS для размещения приложения.|  
|Служба активации Windows (WAS)|Требуется, если необходимо использовать WAS для размещения приложения.|  
  
## <a name="see-also"></a>См. также  
 [Требования к системе](../../../docs/framework/wcf/wcf-system-requirements.md)
