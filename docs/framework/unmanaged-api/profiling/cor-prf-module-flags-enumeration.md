---
title: Перечисление COR_PRF_MODULE_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fee786a7acb87598baabed62067b599907bede
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599147"
---
# <a name="corprfmoduleflags-enumeration"></a>Перечисление COR_PRF_MODULE_FLAGS
Указывает свойства модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Модуль был загружен с диска.|  
|COR_PRF_MODULE_NGEN|Модуль был создан с генератором машинных образов (Ngen.exe).|  
|COR_PRF_MODULE_DYNAMIC|Модуль был создан с методов в <xref:System.Reflection.Emit?displayProperty=nameWithType> пространства имен.|  
|COR_PRF_MODULE_COLLECTIBLE|Время существования модуля осуществляется сборщиком мусора.|  
|COR_PRF_MODULE_RESOURCE|Модуль содержит без метаданных и используются исключительно в качестве ресурса. Является управляемым эквивалентом этот бит <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> метод.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Макет модуля в памяти является плоским, не сопоставлен. Если модуль имеет этот бит установлен, средства профилирования, которые можно прочитать сведения непосредственно из заголовок переносимого исполняемого (PE) файла будет Будьте внимательны при интерпретации относительные виртуальные адреса (RVA) в заголовке.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Среда выполнения Windows тип содержимого флага в метаданных для этого модуля сборки. Это происходит для всех модулей метаданных Windows (.winmd).|  
  
## <a name="remarks"></a>Примечания  
 Биты из COR_PRF_MODULE_FLAGS возвращаются к профилировщику в `pdwModuleFlags` выходного параметра [ICorProfilerInfo3::GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) метод. Возможны некоторые сочетания из двух или более флагов, но не все комбинации.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
