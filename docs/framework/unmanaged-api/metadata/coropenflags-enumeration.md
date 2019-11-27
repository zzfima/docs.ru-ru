---
title: Перечисление CorOpenFlags
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: ad582fc2fd1bd1d2fc9d5a0d483fdb3a51309a10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436503"
---
# <a name="coropenflags-enumeration"></a>Перечисление CorOpenFlags
Содержит значения флага, которые управляют поведением метаданных при открытии файлов манифеста.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ofRead`|Указывает, что файл следует открывать только для чтения.|  
|`ofWrite`|Указывает, что файл следует открывать для записи.<br /><br /> При использовании флага `ofWrite` во время открытия файла .WINMD также следует передавать флаг `ofNoTransform`.|  
|`ofReadWriteMask`|Маска для чтения и записи.|  
|`ofCopyMemory`|Указывает, что файл следует считывать в память. Метаданным следует создавать свою собственную копию.|  
|`ofCacheImage`|Устарело. Этот флаг отклонен.|  
|`ofManifestMetadata`|Устарело. Этот флаг отклонен.|  
|`ofReadOnly`|Указывает, что файл должен быть открыт для чтения и не может быть выполнен вызов `QueryInterface` для [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) .|  
|`ofTakeOwnership`|Указывает, что память была выделена с помощью вызова функции [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) и будет освобождена метаданными.|  
|`ofNoTypeLib`|Устарело. Этот флаг отклонен.|  
|`ofNoTransform`|Указывает, что автоматические преобразования из файла .WINMD следует отключить. Другими словами, проекцию типа среды выполнения Windows на тип платформы .NET Framework следует отключить. Дополнительные сведения см. в статьях [Среда выполнения Windows и среда CLR — внутри .NET и среда выполнения Windows](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).|  
|`ofReserved1`|Зарезервировано для внутреннего использования.|  
|`ofReserved2`|Зарезервировано для внутреннего использования.|  
|`ofReserved`|Зарезервировано для внутреннего использования.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
