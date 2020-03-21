---
title: Метод IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177295"
---
# <a name="imetadataimportenumtypedefs-method"></a>Метод IMetaDataImport::EnumTypeDefs
Перечисляет токены TypeDef, представляющие все типы в текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 (ваут) Указатель на новый регистратор. Это должно быть NULL для первого вызова этого метода.  
  
 `rTypeDefs`  
 (в) Массив, используемый для хранения токенов TypeDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rTypeDefs`.  
  
 `pcTypeDefs`  
 (ваут) Число возвращенных токенов TypeDef `rTypeDefs`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs`вернулся успешно.|  
|`S_FALSE`|Нет токенов для перечисления. В этом `pcTypeDefs` случае, равна нулю.|  
  
## <a name="remarks"></a>Remarks  
 Токен TypeDef представляет собой тип, например класс или интерфейс, а также любой тип, добавленный с помощью механизма расширяемости.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
