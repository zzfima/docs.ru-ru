---
title: Метод IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 381c38542dcde242c0a1a4e71e9b99316328159d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436247"
---
# <a name="imetadatadispenserdefinescope-method"></a>Метод IMetaDataDispenser::DefineScope
Создает новую область в памяти, в которой можно создавать новые метаданные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `rclsid`  
 окне Идентификатор CLSID версии создаваемых структур метаданных. Это значение должно быть CLSID_CorMetaDataRuntime для .NET Framework версии 2,0.  
  
 `dwCreateFlags`  
 окне Флаги, указывающие параметры. Для .NET Framework 2,0 это значение должно быть равно нулю.  
  
 `riid`  
 окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для создания новых метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "Emit". Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="remarks"></a>Заметки  
 `DefineScope` создает набор таблиц метаданных в памяти, создает уникальный идентификатор GUID (идентификатор версии модуля или MVID) для метаданных и создает запись в таблице Module для выдаваемой единицы компиляции.  
  
 Вы можете прикрепить атрибуты к области метаданных в целом с помощью метода [IMetaDataEmit:: сетмодулепропс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::D ефинекустоматтрибуте](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) , в зависимости от ситуации.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
