---
title: Метод IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 106ffeee521f69a73628b1fb6a611abc733583f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431872"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>Метод IMetaDataAssemblyEmit::SetFileProps
Изменяет указанную структуру метаданных `File`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `file`  
 окне Маркер метаданных, указывающий структуру метаданных `File`, которую необходимо изменить.  
  
 `pbHashValue`  
 окне Указатель на хэш-данные, связанные с файлом.  
  
 `cbHashValue`  
 окне Размер в байтах `pbHashValue`.  
  
 `dwFileFlags`  
 окне Побитовое сочетание значений [корфилефлагс](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) , задающих различные атрибуты файла.  
  
## <a name="remarks"></a>Заметки  
 Чтобы создать `File` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинефиле](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
