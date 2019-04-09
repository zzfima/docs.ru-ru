---
title: Структура ASSEMBLY_INFO
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bae19ec18c54eccc7aa54d2d3a006f36ba8ab762
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110881"
---
# <a name="assemblyinfo-structure"></a>Структура ASSEMBLY_INFO
Содержит сведения о сборке, зарегистрированный в глобальном кэше сборок.  
  
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
  
|Член|Описание|  
|------------|-----------------|  
|`cbAssemblyInfo`|Размер в байтах, структуры. Это поле зарезервировано для будущего расширения.|  
|`dwAssemblyFlags`|Флаги, указывающие сведения об установке о сборке. Поддерживаются следующие значения:<br /><br /> -ASSEMBLYINFO_FLAG_INSTALLED значение, которое указывает, что сборка устанавливается. Текущая версия .NET Framework всегда задает `dwAssemblyFlags` этому значению.<br />-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT значение, которое указывает, что сборка является резидентного полезных данных. Текущая версия .NET Framework никогда не задает `dwAssemblyFlags` этому значению.|  
|`uliAssemblySizeInKB`|Общий размер в килобайтах, файлов, содержащих сборки.|  
|`pszCurrentAssemblyPathBuf`|Указатель на буфер строки, содержащий текущий путь к файлу манифеста. Путь должен заканчиваться символом null.|  
|`cchBuf`|Число расширенных символов, включая завершающий символ null, который `pszCurrentAssemblyPathBuf` содержит.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
