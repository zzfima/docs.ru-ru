---
title: Метод IMetaDataImport::GetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8832d6c19108459ffe261a5cf66f921ff521ddf9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465833"
---
# <a name="imetadataimportgetrva-method"></a>Метод IMetaDataImport::GetRVA
Возвращает относительный виртуальный адрес (RVA) и флаги реализации метода или поля, представленного указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 [in] MethodDef или FieldDef токен метаданных, представляющий возвращаемого RVA для объекта кода. Если токен FieldDef, поле должно быть глобальной переменной.  
  
 `pulCodeRVA`  
 [out] Указатель на относительный виртуальный адрес объекта кода, представленного маркером.  
  
 `pdwImplFlags`  
 [out] Указатель на флаги реализации метода. Это значение является битовой [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) перечисления. Значение `pdwImplFlags` действителен только если `tk` является токеном MethodDef.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
