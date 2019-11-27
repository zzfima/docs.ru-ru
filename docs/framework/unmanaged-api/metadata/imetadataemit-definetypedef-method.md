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
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450212"
---
# <a name="imetadataemitdefinetypedef-method"></a>Метод IMetaDataEmit::DefineTypeDef
Создает определение типа для типа среды CLR и получает маркер метаданных для этого определения типа.  
  
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
 окне Имя типа в Юникоде.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` атрибуты. Это битовая маска `CoreTypeAttr` значений.  
  
 `tkExtends`  
 окне Маркер базового класса. Это должен быть либо `mdTypeDef`, либо маркер `mdTypeRef`.  
  
 `rtkImplements`  
 окне Массив токенов, указывающий интерфейсы, реализуемые этим классом или интерфейсом.  
  
 `ptd`  
 заполняет Назначенный маркер `mdTypeDef`.  
  
## <a name="remarks"></a>Примечания  
 Флаг в `dwTypeDefFlags` указывает, является ли создаваемый тип ссылочным типом системы общих типов (класс или интерфейс) или типом значения системы общего типа.  
  
 В зависимости от предоставленных параметров этот метод, как побочный результат, может также создавать запись `mdInterfaceImpl` для каждого интерфейса, унаследованного или реализуемого этим типом. Однако этот метод не возвращает ни одного из этих маркеров `mdInterfaceImpl`. Если клиент хочет позже добавить или изменить маркер `mdInterfaceImpl`, он должен использовать интерфейс `IMetaDataImport`, чтобы перечислить их. Если вы хотите использовать семантику COM интерфейса `[default]`, необходимо указать интерфейс по умолчанию в качестве первого элемента в `rtkImplements`; настраиваемый атрибут, заданный для класса, указывает, что класс имеет интерфейс по умолчанию (который всегда считается первым маркером `mdInterfaceImpl`, объявленным для класса).  
  
 Каждый элемент массива `rtkImplements` содержит маркер `mdTypeDef` или `mdTypeRef`. Последний элемент в массиве должен быть `mdTokenNil`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
