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
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175503"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Метод IMetaDataImport::EnumInterfaceImpls
Перечисляет все интерфейсы, реализованные `TypeDef`указанным .
  
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
 (в, вне) Указатель на регистратор.  
  
 `td`  
 (в) В перечне будет перечислен токен TypeDef, токены которого MethodDef, представляющие реализации интерфейса.  
  
 `rImpls`  
 (ваут) Массив, используемый для хранения токенов MethodDef.  
  
 `cMax`  
 (в) Максимальная длина `rImpls` массива.  
  
 `pcImpls`  
 (ваут) Фактическое количество токенов, `rImpls`возвращенных в .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`вернулся успешно.|  
|`S_FALSE`|Нет токенов MethodDef для перечисления. В этом `pcImpls` случае, устанавливается до нуля.|  

## <a name="remarks"></a>Remarks

Перечисление возвращает коллекцию `mdInterfaceImpl` токенов для каждого интерфейса, реализованного указанным `TypeDef`. Токены интерфейса возвращаются в порядке, указанном интерфейсами (через `DefineTypeDef` или). `SetTypeDefProps` Свойства возвращенных `mdInterfaceImpl` токенов можно поставить под вопрос с помощью [GetInterfaceImplProps.](imetadataimport-getinterfaceimplprops-method.md)
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
