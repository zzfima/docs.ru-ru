---
title: Метод IMetaDataEmit::SetCustomAttributeValue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: fd5e71071de9e6afebc8f1848e0af8835f22c9bf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448125"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a>Метод IMetaDataEmit::SetCustomAttributeValue
Задает или обновляет значение настраиваемого атрибута, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинекустоматтрибуте](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pcv`  
 окне Токен целевого настраиваемого атрибута.  
  
 `pCustomAttribute`  
 окне Указатель на массив, содержащий настраиваемый атрибут.  
  
 `cbCustomAttribute`  
 окне Размер настраиваемого атрибута в байтах.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
