---
title: Метод IMetaDataImport::GetCustomAttributeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
ms.openlocfilehash: 9a80336db4a5a8d7cfdebb7eb8d25bcb8f96e87c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437646"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>Метод IMetaDataImport::GetCustomAttributeProps
Возвращает значение пользовательского атрибута по указанному токену метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cv`  
 [in] Токен метаданных, который представляет извлекаемый пользовательский атрибут.  
  
 `ptkObj`  
 [out, optional] Токен метаданных, представляющий объект, который изменяет пользовательский атрибут. Это значение может быть любым типом токена метаданных, кроме `mdCustomAttribute`.  
  
 `ptkType`  
 [out, optional] Токен метаданных `mdMethodDef` или `mdMemberRef`, представляющий <xref:System.Type> возвращаемого пользовательского атрибута.  
  
 `ppBlob`  
 [out, optional] Указатель на массив данных, который является значением пользовательского атрибута.  
  
 `pcbSize`  
 [out, optional] Размер в байтах данных, возвращаемых в *`ppBlob`.  
  
## <a name="remarks"></a>Заметки  
 Пользовательский атрибут хранится в виде массива данных, в формате, который поддерживается подсистемой метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Included as a resource in MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
