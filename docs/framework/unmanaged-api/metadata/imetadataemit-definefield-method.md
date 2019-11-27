---
title: Метод IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432545"
---
# <a name="imetadataemitdefinefield-method"></a>Метод IMetaDataEmit::DefineField
Создает определение для поля с указанной сигнатурой метаданных и получает маркер для этого определения поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне Токен `mdTypeDef` для включающего класса или интерфейса.  
  
 `szName`  
 окне Имя поля в Юникоде.  
  
 `dwFieldFlags`  
 окне Атрибуты поля. Это битовая маска `CorFieldAttr` значений.  
  
 `pvSigBlob`  
 окне Подпись поля в виде большого двоичного объекта.  
  
 `cbSigBlob`  
 окне Число байтов в `pvSigBlob`.  
  
 `dwCPlusTypeFlag`  
 окне *\** `ELEMENT_TYPE_`для постоянного значения. Это `CorElementType` значение. Если для поля не определено постоянное значение, используйте `ELEMENT_TYPE_END`.  
  
 `pValue`  
 окне Постоянное значение для поля.  
  
 `cchValue`  
 окне Размер (в Юникоде) символов `pValue`.  
  
 `pmd`  
 заполняет Назначенный маркер `mdFieldDef`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
