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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d64a1ef21cd4fa4224609c7cd415c1611313769
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777545"
---
# <a name="imetadataemitdefineparam-method"></a>Метод IMetaDataEmit::DefineParam
Создает определение параметра с указанной сигнатурой метода, который ссылается указанный токен и получает маркер для данного определения параметра.  
  
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
 [in] Токен для метода, параметр которого определяется.  
  
 `ulParamSeq`  
 [in] Порядковый номер параметра.  
  
 `szName`  
 [in] Имя параметра в формате Юникод.  
  
 `dwParamFlags`  
 [in] Флаги для параметра. Это битовая маска `CorParamAttr` значения.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** для постоянного значения.  
  
 `pValue`  
 [in] Постоянное значение для параметра.  
  
 `cchValue`  
 [in] Размер в символы Юникода из `pValue`.  
  
 `ppd`  
 [out] `mdParamDef` Маркер, назначенный.  
  
## <a name="remarks"></a>Примечания  
 Последовательность значений элементов в `ulParamSeq` начинаются с 1 для параметров. Возвращаемое значение имеет порядковый номер 0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
