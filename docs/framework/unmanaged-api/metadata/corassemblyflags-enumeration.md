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
ms.openlocfilehash: 9d6ec37bbd8750c27a41b5f18180c7726cdcd483
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442844"
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
  
|Член|Описание|  
|------------|-----------------|  
|`afPublicKey`|Указывает, что ссылка содержит полный, не хэшированный открытый ключ.|  
|`afPA_None`|Указывает, что архитектура процессора не задана.|  
|`afPA_MSIL`|Указывает, что архитектура процессора нейтральный (PE32).|  
|`afPA_x86`|Указывает, что архитектура процессора — x86 (PE32).|  
|`afPA_IA64`|Указывает архитектуру процессора Itanium (PE32 +).|  
|`afPA_AMD64`|Указывает, что архитектура процессора — AMD X64 (PE32 +).|  
|`afPA_ARM`|Указывает архитектуру процессора ARM (PE32).|  
|`afPA_NoPlatform`|Указывает, что сборка является ссылочной сборкой; Это значит относится к любой архитектуры, но не может работать на любой архитектуры. Таким образом, флаг совпадает со значением `afPA_Mask`.|  
|`afPA_Specified`|Указывает, что флаги архитектуры процессора должны распространяться на `AssemblyRef` запись.|  
|`afPA_Mask`|Маска, описывающая архитектуру процессора.|  
|`afPA_FullMask`|Указывает, что включено описание архитектуры процессора.|  
|`afPA_Shift`|Указывает число смещений во флагах архитектуры процессора и из индекса.|  
|`afEnableJITcompileTracking`|Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Указывает, соответствующее значение в <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> из <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Указывает, что сборки могут быть перенаправлены во время выполнения на сборку из другого издателя.|  
|`afContentType_Mask`|Маска, которая описывает тип содержимого.|  
|`afContentType_Default`|Указывает тип содержимого по умолчанию.|  
|`afContentType_WindowsRuntime`|Указывает [!INCLUDE[wrt](../../../../includes/wrt-md.md)] тип содержимого.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
