---
title: "Структура ASSEMBLY_INFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 215d80c3d207c2f50cfbd74386915b0467692b57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyinfo-structure"></a>Структура ASSEMBLY_INFO
Содержит сведения о сборке, которая зарегистрирована в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`cbAssemblyInfo`|Размер в байтах структуры. Это поле зарезервировано для будущего расширения.|  
|`dwAssemblyFlags`|Флаги, указывающие установки сведений о сборке. Поддерживаются следующие значения:<br /><br /> -ASSEMBLYINFO_FLAG_INSTALLED значение, которое указывает, что сборка установлена. Текущую версию платформы .NET Framework, всегда устанавливает `dwAssemblyFlags` это значение.<br />-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT значение, которое указывает, что сборка является резидентной полезных данных. Текущую версию платформы .NET Framework никогда не задает `dwAssemblyFlags` это значение.|  
|`uliAssemblySizeInKB`|Общий размер в килобайтах, файлов, содержащих сборки.|  
|`pszCurrentAssemblyPathBuf`|Указатель на буфер строки, содержащий текущий путь к файлу манифеста. Путь должен заканчиваться символом null.|  
|`cchBuf`|Число расширенных символов, включая завершающий символ null, `pszCurrentAssemblyPathBuf` содержит.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
