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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f99fb7a693c47b257abe9c0b783856179fc9f0eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582384"
---
# <a name="corassemblyflags-enumeration"></a>Перечисление CorAssemblyFlags
Содержит значения, которые описывают метаданные, применяемые к компиляции сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`afPublicKey`|Указывает, что ссылки на сборку содержит полный, не хэшированный открытый ключ.|  
|`afPA_None`|Указывает, что архитектура процессора не определен.|  
|`afPA_MSIL`|Указывает, что архитектура процессора является нейтральный (PE32).|  
|`afPA_x86`|Указывает архитектуру процессора x86 (PE32).|  
|`afPA_IA64`|Указывает архитектуру процессора Itanium (PE32 +).|  
|`afPA_AMD64`|Указывает архитектуру процессора AMD X64 (PE32 +).|  
|`afPA_ARM`|Указывает архитектуру процессора ARM (PE32).|  
|`afPA_NoPlatform`|Указывает, что сборка является ссылочной сборки; то есть применяется к любой архитектуры, но не могут работать на компьютерах с любой архитектурой. Таким образом, флаг совпадает со значением `afPA_Mask`.|  
|`afPA_Specified`|Указывает, что флаги архитектуры процессора должны распространяться на `AssemblyRef` записи.|  
|`afPA_Mask`|Маска, которая описывает архитектуру процессора.|  
|`afPA_FullMask`|Указывает, что включено описание архитектуры процессора.|  
|`afPA_Shift`|Указывает число смещений во флагах архитектуры процессора и из индекса.|  
|`afEnableJITcompileTracking`|Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Указывает, что сборка может быть перенацелена во время выполнения на сборку от другого издателя.|  
|`afContentType_Mask`|Маска, которая описывает тип содержимого.|  
|`afContentType_Default`|Указывает тип содержимого по умолчанию.|  
|`afContentType_WindowsRuntime`|Указывает [!INCLUDE[wrt](../../../../includes/wrt-md.md)] тип содержимого.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
