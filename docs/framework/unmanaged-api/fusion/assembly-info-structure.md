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
ms.openlocfilehash: 390ab4881396bbc01337d087f05b6066153bfed1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795489"
---
# <a name="assembly_info-structure"></a>Структура ASSEMBLY_INFO
Содержит сведения о сборке, зарегистрированной в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|`cbAssemblyInfo`|Размер структуры в байтах. Это поле зарезервировано для будущего расширения.|  
|`dwAssemblyFlags`|Флаги, указывающие сведения об установке сборки. Поддерживаются следующие значения:<br /><br /> — Значение ASSEMBLYINFO_FLAG_INSTALLED, указывающее, что сборка установлена. Текущая версия .NET Framework всегда задает `dwAssemblyFlags` это значение.<br />— Значение ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, которое указывает, что сборка является резидентной полезной нагрузкой. Текущая версия .NET Framework никогда не задает `dwAssemblyFlags` это значение.|  
|`uliAssemblySizeInKB`|Общий размер файлов, содержащихся в сборке, в килобайтах.|  
|`pszCurrentAssemblyPathBuf`|Указатель на строковый буфер, содержащий текущий путь к файлу манифеста. Путь должен заканчиваться нулевым символом.|  
|`cchBuf`|Количество расширенных символов, включая знак завершения `pszCurrentAssemblyPathBuf` null, содержащий.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры Fusion](fusion-structures.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
