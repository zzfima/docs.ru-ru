---
title: "Метод IMetaDataEmit::SetPropertyProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fe79846b9fd576941c706b48a7aed0667c264a3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpropertyprops-method"></a>Метод IMetaDataEmit::SetPropertyProps
Задает функции сохранения в метаданных для свойства, определенные во время предыдущего вызова для [метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pr`  
 [in] Маркер для изменения свойства  
  
 `dwPropFlags`  
 [in] Флаги свойства.  
  
 `dwCPlusTypeFlag`  
 [in] Тип значения по умолчанию этого свойства.  
  
 `pValue`  
 [in] Значение по умолчанию для свойства.  
  
 `cchValue`  
 [in] Количество (Юникод) символы в `pValue`.  
  
 `mdSetter`  
 [in] Метод, который задает значение свойства.  
  
 `mdGetter`  
 [in] Метод, который возвращает значение свойства.  
  
 `rmdOtherMethods[]`  
 [in] Массив из других методов, связанное со свойством. Этот массив `mdTokenNil` токена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
