---
title: "Интерфейс IReferenceIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a>Интерфейс IReferenceIdentity
Представляет ссылку на уникальную подпись объекта кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Получает указатель интерфейса на новый `IReferenceIdentity` экземпляр, идентичным этому `IReferenceIdentity`, за исключением изменения указанного атрибута.|  
|`IReferenceIdentity::EnumAttributes`|Возвращает указатель интерфейса `IEnumIDENTITY_ATTRIBUTE` экземпляр, содержащий атрибуты, связанные с этим `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Возвращает значение атрибута в указанное пространство имен, с указанным именем.|  
|`IReferenceIdentity::SetAttribute`|Задает атрибут, имеющий указанное пространство имен и именем указанное значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Фьюжн-интерфейсы](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Интерфейс IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
