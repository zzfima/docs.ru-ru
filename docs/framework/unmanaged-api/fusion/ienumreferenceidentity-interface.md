---
title: "Интерфейс IEnumReferenceIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1af31c72770947c33f358a9689bac6fd95ef53c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ienumreferenceidentity-interface"></a>Интерфейс IEnumReferenceIdentity
Служит в качестве перечислитель для коллекции `IReferenceIdentity` объектов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Получает указатель интерфейса на новый `IEnumReferenceIdentity` , содержащий те же элементы, как это `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Возвращает заданное число `IReferenceIdentity` объектов, начиная с текущей позиции.|  
|`IEnumReferenceIdentity::Reset`|Перемещает указатель на начало `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Интерфейс IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
