---
title: Метод IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440237"
---
# <a name="imetadataimportenumcustomattributes-method"></a>Метод IMetaDataImport::EnumCustomAttributes
Перечисляет токены определения пользовательских атрибутов, связанные с указанным типом или членом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на возвращаемый перечислитель.  
  
 `tk`  
 окне Токен для области перечисления или ноль для всех настраиваемых атрибутов.  
  
 `tkType`  
 окне Токен для конструктора типа атрибутов для перечисления или `null` для всех типов.  
  
 `rCustomAttributes`  
 заполняет Массив токенов настраиваемых атрибутов.  
  
 `cMax`  
 [in] Максимальный размер массива `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, необязательно] Фактическое число значений токенов, возвращаемых в `rCustomAttributes`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` успешно возвращено.|  
|`S_FALSE`|Нет настраиваемых атрибутов для перечисления. В этом случае `pcCustomAttributes` равно нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
