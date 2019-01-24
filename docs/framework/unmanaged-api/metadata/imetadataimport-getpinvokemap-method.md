---
title: Метод IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2aed3367e20e32a387c8a1c58ead2899fbf0dcb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521443"
---
# <a name="imetadataimportgetpinvokemap-method"></a>Метод IMetaDataImport::GetPinvokeMap
Возвращает токен ModuleRef, представляющий целевую сборку вызова PInvoke.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tk`  
 [in] Токен FieldDef или MethodDef, чтобы получить метаданные сопоставления PInvoke для.  
  
 `pdwMappingFlags`  
 [out] Указатель на флаги, используемые для сопоставления. Это значение является битовой [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) перечисления.  
  
 `szImportName`  
 [out] Имя целевой неуправляемой библиотеки DLL.  
  
 `cchImportName`  
 [in] Размер в расширенных символах `szImportName`.  
  
 `pchImportName`  
 [out] Число расширенных символов, возвращаемых в `szImportName`.  
  
 `pmrImportDLL`  
 [out] Указатель на токен ModuleRef, представляющий неуправляемый целевой объект библиотеки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
