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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136504"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Метод IMetaDataImport::EnumInterfaceImpls
Перечисляет все интерфейсы, реализованные с помощью указанного `TypeDef`. 
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 [in, out] Указатель на перечислитель.  
  
 `td`  
 [in] Токен TypeDef, которого токены MethodDef, представляющие реализации интерфейса, которые необходимо перечислить.  
  
 `rImpls`  
 [out] Массив, используемый для хранения токенов MethodDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rImpls`.  
  
 `pcImpls`  
 [out] Фактическое число маркеров, возвращаемых в `rImpls`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры MethodDef для перечисления отсутствуют. В этом случае `pcImpls` присваивается нулевое значение.|  

## <a name="remarks"></a>Примечания

Перечисление возвращает коллекцию `mdInterfaceImpl` маркеры для каждого интерфейса, реализуемый указанного `TypeDef`. Интерфейс маркеры возвращаются в порядке, указанном интерфейсы были (через `DefineTypeDef` или `SetTypeDefProps`). Свойствам возвращенного типа сущности `mdInterfaceImpl` маркеры можно запросить с помощью [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
