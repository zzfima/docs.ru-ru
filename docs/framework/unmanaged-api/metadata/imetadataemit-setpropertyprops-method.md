---
title: Метод IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d836abb63aec0ffd72fb54d342e36bae7191a533
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489037"
---
# <a name="imetadataemitsetpropertyprops-method"></a>Метод IMetaDataEmit::SetPropertyProps
Задает хранится в метаданных для свойства, определенные с помощью предыдущего вызова функции [метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pr`  
 [in] Токен для свойства, которые необходимо изменить  
  
 `dwPropFlags`  
 [in] Флаги свойства.  
  
 `dwCPlusTypeFlag`  
 [in] Тип значения свойства по умолчанию.  
  
 `pValue`  
 [in] Значение по умолчанию для свойства.  
  
 `cchValue`  
 [in] Количество (Юникод) символы в `pValue`.  
  
 `mdSetter`  
 [in] Метод, который задает значение свойства.  
  
 `mdGetter`  
 [in] Метод, который возвращает значение свойства.  
  
 `rmdOtherMethods[]`  
 [in] Массив, другие методы, связанные со свойством. Этот массив `mdTokenNil` токена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
