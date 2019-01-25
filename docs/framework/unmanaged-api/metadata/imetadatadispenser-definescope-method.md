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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f9cac2b59f783a81663af0c5eb148367d54e8aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605193"
---
# <a name="imetadatadispenserdefinescope-method"></a>Метод IMetaDataDispenser::DefineScope
Создает новую область в памяти, в котором можно создать новые метаданные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `rclsid`  
 [in] CLSID создаваемого версии структуры метаданных. Это значение должно быть CLSID_CorMetaDataRuntime для платформы .NET Framework версии 2.0.  
  
 `dwCreateFlags`  
 [in] Флаги, определяющие параметры. Это значение должно быть ноль для .NET Framework 2.0.  
  
 `riid`  
 [in] IID интерфейса новых метаданных должна быть возвращена. вызывающий объект будет использовать интерфейс для создания новых метаданных.  
  
 Значение `riid` необходимо указать один из интерфейсов «выдает». Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [out] Указатель на возвращенный интерфейс.  
  
## <a name="remarks"></a>Примечания  
 `DefineScope` Создает набор таблиц метаданных в памяти, уникальный идентификатор GUID (идентификатор версии модуля или MVID) для метаданных и создает запись в таблице модуля для блоком компиляции.  
  
 Можно присоединить атрибуты в область действия метаданных в целом, используя [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) метод соответствующим образом.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
