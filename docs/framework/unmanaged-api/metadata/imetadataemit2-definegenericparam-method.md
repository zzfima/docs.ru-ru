---
title: Метод IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 3898b095809e2b84f71aba2036f4d7a294dfdf6a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444650"
---
# <a name="imetadataemit2definegenericparam-method"></a>Метод IMetaDataEmit2::DefineGenericParam
Создает определение для параметра универсального типа и получает маркер для этого параметра универсального типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 окне Маркер `mdTypeDef` или `mdMethodDef`, представляющий метод или конструктор, для которого определяется универсальный параметр.  
  
 `ulParamSeq`  
 окне Индекс универсального параметра.  
  
 `dwParamFlags`  
 окне Значение перечисления [корженерикпараматтр](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) , описывающее тип универсального параметра.  
  
 `szname`  
 окне Имя параметра.  
  
 `reserved`  
 окне Этот параметр зарезервирован для расширения в будущем.  
  
 `rtkConstraints`  
 окне Массив ограничений типа, заканчивающийся нулем. Элементы массива должны быть `mdTypeDef`, `mdTypeRef`или маркером метаданных `mdTypeSpec`.  
  
 `pgp`  
 заполняет Токен, представляющий универсальный параметр.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
