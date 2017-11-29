---
title: "Метод IManagedObject::GetSerializedBuffer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetSerializedBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d326fba5cbdb38dd2c5d07f4f69f3f2d8e75114c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imanagedobjectgetserializedbuffer-method"></a>Метод IManagedObject::GetSerializedBuffer
Возвращает строковое представление данного управляемого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pBSTR`  
 [out] Указатель на строку, являющуюся сериализованный объект.  
  
## <a name="remarks"></a>Примечания  
 `GetSerializedBuffer` Метод сериализует объект, поэтому он может быть маршалирован клиенту.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IManagedObject-интерфейс](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
