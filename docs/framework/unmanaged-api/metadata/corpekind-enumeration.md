---
title: Перечисление CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 74670a1477546066145bd4bbf2f123a252e10b55
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436470"
---
# <a name="corpekind-enumeration"></a>Перечисление CorPEKind
Содержит значения, описывающие переносимый исполняемый файл (PE), возвращенный при вызове [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`peNot`|Указывает, что этот файл не является PE-файлом.|  
|`peILOnly`|Указывает, что этот PE файл содержит только управляемый код.|  
|`pe32BitRequired`|Указывает, что этот PE файл выполняет вызовы Win32.|  
|`pe32Plus`|Указывает, что этот PE-файл выполняется на 64-разрядной платформе.|  
|`pe32Unmanaged`|Указывает, что этот PE-файл является машинным кодом.|  
|pe32BitPreferred|Указывает, что этот PE-файл является нейтральным к платформе и предпочитает загрузку в 32-разрядной среде.|  
  
## <a name="remarks"></a>Примечания  
 Эти значения можно использовать в побитовых сочетаниях.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
