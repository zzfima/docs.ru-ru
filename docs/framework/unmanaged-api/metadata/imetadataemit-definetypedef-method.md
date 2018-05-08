---
title: Метод IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54691785e3b2619b5f4a2eecc510800b4b5cee07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefinetypedef-method"></a>Метод IMetaDataEmit::DefineTypeDef
Создает определение типа для типа среды выполнения и получает маркер метаданных для этого определения типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szTypeDef`  
 [in] Имя типа в Юникоде.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` атрибуты. Это битовая маска `CoreTypeAttr` значения.  
  
 `tkExtends`  
 [in] Токен базового класса. Он должен быть либо `mdTypeDef` или `mdTypeRef` токена.  
  
 `rtkImplements`  
 [in] Массив маркеров, указав интерфейсов, реализуемых данного класса или интерфейса.  
  
 `ptd`  
 [out] `mdTypeDef` Маркер, назначенный.  
  
## <a name="remarks"></a>Примечания  
 Флаг в `dwTypeDefFlags` указывает, является ли тип, который создается общий тип системы ссылочным типом (класс или интерфейс) или общий тип системный тип значения.  
  
 В зависимости от параметров, указанные, этот метод в качестве побочного эффекта, могут также создавать `mdInterfaceImpl` записей для каждого интерфейса, реализуемый этим типом или унаследован. Однако этот метод не возвращает любое из этих `mdInterfaceImpl` маркеры. Если клиент хочет позднее добавить или изменить `mdInterfaceImpl` токенов, он должен использовать `IMetaDataImport` интерфейса для их перебора. Если требуется использовать семантику COM `[default]` интерфейса, необходимо предоставить интерфейс по умолчанию как первый элемент в `rtkImplements`; задать класса настраиваемого атрибута покажет, что класс имеет интерфейс по умолчанию (который всегда считается Сначала `mdInterfaceImpl` маркер, объявленным для класса).  
  
 Каждый элемент `rtkImplements` массива содержит `mdTypeDef` или `mdTypeRef` токена. Последним элементом в массиве должен быть `mdTokenNil`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
