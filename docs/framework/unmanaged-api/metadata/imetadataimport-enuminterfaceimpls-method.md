---
title: Метод IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338063"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Метод IMetaDataImport::EnumInterfaceImpls
Перечисляет все интерфейсы, реализованные указанным `TypeDef`. 
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `td`  
 окне Токен TypeDef, маркеры MethodDef которого представляют реализации интерфейса для перечисления.  
  
 `rImpls`  
 заполняет Массив, используемый для хранения маркеров MethodDef.  
  
 `cMax`  
 окне Максимальная длина массива `rImpls`.  
  
 `pcImpls`  
 заполняет Фактическое число токенов, возвращаемых в `rImpls`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` успешно возвращено.|  
|`S_FALSE`|Отсутствуют токены MethodDef для перечисления. В этом случае `pcImpls` имеет значение 0.|  

## <a name="remarks"></a>Заметки

Перечисление Возвращает коллекцию токенов `mdInterfaceImpl` для каждого интерфейса, реализованного с помощью указанного `TypeDef`. Маркеры интерфейса возвращаются в том порядке, в котором были указаны интерфейсы (с помощью `DefineTypeDef` или `SetTypeDefProps`). Свойства возвращенных маркеров `mdInterfaceImpl` можно запрашивать с помощью [жетинтерфацеимплпропс](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
