---
title: Перечисление CorAssemblyFlags
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
ms.openlocfilehash: fda890cee5f513ea8cf7e82e710f5451a860c49f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443908"
---
# <a name="corassemblyflags-enumeration"></a>Перечисление CorAssemblyFlags
Содержит значения, которые описывают метаданные, применяемые к компиляции сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`afPublicKey`|Указывает, что ссылка на сборку содержит полный, нехэшированный открытый ключ.|  
|`afPA_None`|Указывает, что архитектура процессора не определена.|  
|`afPA_MSIL`|Указывает, что архитектура процессора нейтральна (формат PE32).|  
|`afPA_x86`|Указывает, что архитектура процессора — x86 (формат PE32).|  
|`afPA_IA64`|Указывает, что архитектура процессора — Itanium (формат PE32 +).|  
|`afPA_AMD64`|Указывает, что архитектура процессора — это AMD x64 (формат PE32 +).|  
|`afPA_ARM`|Указывает, что архитектура процессора — ARM (формат PE32).|  
|`afPA_NoPlatform`|Указывает, что сборка является ссылочной сборкой; то есть он применяется к любой архитектуре, но не может работать в любой архитектуре. Таким образом, флаг будет таким же, как `afPA_Mask`.|  
|`afPA_Specified`|Указывает, что флаги архитектуры процессора должны распространяться на запись `AssemblyRef`.|  
|`afPA_Mask`|Маска, описывающая архитектуру процессора.|  
|`afPA_FullMask`|Указывает, что включено описание архитектуры процессора.|  
|`afPA_Shift`|Указывает число смещений в флагах архитектуры процессора в индекс и из него.|  
|`afEnableJITcompileTracking`|Указывает соответствующее значение из <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Указывает соответствующее значение из <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Указывает, что сборка может быть перенацелена во время выполнения в сборку из другого издателя.|  
|`afContentType_Mask`|Маска, описывающая тип содержимого.|  
|`afContentType_Default`|Указывает тип содержимого по умолчанию.|  
|`afContentType_WindowsRuntime`|Указывает тип содержимого среда выполнения Windows.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
