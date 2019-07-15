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
ms.openlocfilehash: 0777151d10149ec7311a7761bc7f6bff5ba98e0e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777488"
---
# <a name="imetadataemitdefinetypedef-method"></a>Метод IMetaDataEmit::DefineTypeDef
Создает определение типа для типа среды выполнения и получает маркер метаданных для этого определения типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szTypeDef`  
 [in] Имя типа в формате Юникод.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` атрибуты. Это битовая маска `CoreTypeAttr` значения.  
  
 `tkExtends`  
 [in] Токен базового класса. Он должен быть либо `mdTypeDef` или `mdTypeRef` токена.  
  
 `rtkImplements`  
 [in] Массив токенов, указав интерфейсы, реализуемые этот класс или интерфейс.  
  
 `ptd`  
 [out] `mdTypeDef` Маркер, назначенный.  
  
## <a name="remarks"></a>Примечания  
 Флаг в `dwTypeDefFlags` указывает, является ли тип, который создается общий тип системы ссылочным типом (класс или интерфейс) или общие системные типы значений типа.  
  
 В зависимости от параметров, содержащихся, этот метод в качестве побочного эффекта, может также создавать `mdInterfaceImpl` записей для каждого интерфейса, реализуемый этим типом или унаследован. Тем не менее, этот метод не возвращает любое из этих `mdInterfaceImpl` маркеры. Если клиент хочет позже добавить или изменить `mdInterfaceImpl` маркеров, он должен использовать `IMetaDataImport` интерфейс для их перебора. Если вы хотите использовать семантику COM `[default]` интерфейс, должны предоставлять интерфейс по умолчанию, как первый элемент в `rtkImplements`; задать класса настраиваемого атрибута укажет, что класс имеет интерфейс по умолчанию (который всегда предполагается, что Сначала `mdInterfaceImpl` маркер, объявленным для класса).  
  
 Каждый элемент `rtkImplements` массива содержит `mdTypeDef` или `mdTypeRef` токена. Последним элементом в массиве должен быть `mdTokenNil`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
