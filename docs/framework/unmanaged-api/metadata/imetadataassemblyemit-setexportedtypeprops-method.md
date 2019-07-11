---
title: Метод IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4be840760782789aa91e5519f60374aca2e3941
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775260"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>Метод IMetaDataAssemblyEmit::SetExportedTypeProps
Изменяет указанную структуру метаданных `ExportedType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ct`  
 [in] Токен метаданных, указывающее `ExportedType` изменение структуры метаданных.  
  
 `tkImplementation`  
 [in] Токен типа `File`, `AssemblyRef`, или `ExportedType`, указывающий реализации этого типа.  
  
 `tkTypeDef`  
 [in] `TypeDef` Токена, на которые ссылается файл кода.  
  
 `dwExportedTypeFlags`  
 [in] Побитовое сочетание значений, определяющих атрибуты типа.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `ExportedType` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
