---
title: Метод IMetaDataEmit::DefineParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177691"
---
# <a name="imetadataemitdefineparam-method"></a>Метод IMetaDataEmit::DefineParam
Создает определение параметров с указанной подписью для метода, на который ссылается указанный маркер, и получает маркер для определения этого параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>Параметры  
 `md`  
 (в) Токен для метода, параметр которого определяется.  
  
 `ulParamSeq`  
 (в) Номер последовательности параметра.  
  
 `szName`  
 (в) Название параметра в Unicode.  
  
 `dwParamFlags`  
 (в) Флаги для параметра. Это битмаска ценностей. `CorParamAttr`  
  
 `dwCPlusTypeFlag`  
 (в) `ELEMENT_TYPE_` для постоянного *\** значения.  
  
 `pValue`  
 (в) Постоянное значение параметра.  
  
 `cchValue`  
 (в) Размер, в unicode символов, из `pValue`.  
  
 `ppd`  
 (ваут) Назначенный `mdParamDef` маркер.  
  
## <a name="remarks"></a>Remarks  
 Значения последовательности `ulParamSeq` начинаются с 1 для параметров. Значение возврата имеет число последовательности 0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
