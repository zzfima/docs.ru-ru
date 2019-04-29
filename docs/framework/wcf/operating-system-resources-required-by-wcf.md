---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955224"
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
