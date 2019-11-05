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
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109218"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`cbAssemblyInfo`|Размер структуры в байтах. Это поле зарезервировано для будущего расширения.|  
|`dwAssemblyFlags`|Флаги, указывающие сведения об установке сборки. Поддерживаются следующие значения:<br /><br /> — Значение ASSEMBLYINFO_FLAG_INSTALLED, указывающее, что сборка установлена. Текущая версия .NET Framework всегда задает для `dwAssemblyFlags` это значение.<br />— Значение ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, которое указывает, что сборка является резидентной полезной нагрузкой. Текущая версия .NET Framework никогда не задает `dwAssemblyFlags` этому значению.|  
|`uliAssemblySizeInKB`|Общий размер файлов, содержащихся в сборке, в килобайтах.|  
|`pszCurrentAssemblyPathBuf`|Указатель на строковый буфер, содержащий текущий путь к файлу манифеста. Путь должен заканчиваться нулевым символом.|  
|`cchBuf`|Количество расширенных символов, включая знак завершения null, который `pszCurrentAssemblyPathBuf` содержит.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры Fusion](fusion-structures.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
