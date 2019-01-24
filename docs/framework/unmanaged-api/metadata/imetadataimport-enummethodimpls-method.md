---
title: Метод IMetaDataImport::EnumMethodImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfd41a232a3284f79e4229a8845bf5a34f9d1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574772"
---
# <a name="imetadataimportenummethodimpls-method"></a>Метод IMetaDataImport::EnumMethodImpls
Перечисляет токены MethodBody и MethodDeclaration, представляющие методы указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `td`  
 [in] TypeDef для типа маркера, реализации метода для перечисления.  
  
 `rMethodBody`  
 [out] Массив для хранения токены MethodBody.  
  
 `rMethodDecl`  
 [out] Массив для хранения токенов MethodDeclaration.  
  
 `cMax`  
 [in] Максимальный размер `rMethodBody` и `rMethodDecl` массивов.  
  
 `pcTokens`  
 [in] Фактическое число методов, возвращаемый в `rMethodBody` и `rMethodDecl`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodImpls` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры нет метода для перечисления. В этом случае `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
