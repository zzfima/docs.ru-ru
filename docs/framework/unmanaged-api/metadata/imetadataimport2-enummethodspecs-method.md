---
title: Метод IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 4a1de144163ec2b4952bd16b59fb1c92b706631b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428295"
---
# <a name="imetadataimport2enummethodspecs-method"></a>Метод IMetaDataImport2::EnumMethodSpecs
Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель для `rMethodSpecs`.  
  
 `tk`  
 окне Токен MemberRef или MethodDef, представляющий метод, для которого необходимо перечислить маркеры MethodSpec. Если значение `tk` равно 0 (нулю), будут перечислены все токены MethodSpec в области.  
  
 `rMethodSpecs`  
 заполняет Массив токенов MethodSpec для перечисления.  
  
 `cMax`  
 окне Запрошенное максимальное число токенов, помещаемых в `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 заполняет Возвращенное число токенов, помещенных в `rMethodSpecs`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` успешно возвращено.|  
|`S_FALSE`|у `phEnum` нет элементов Member. В этом случае `pcMethodSpecs` имеет значение 0 (ноль).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
