---
title: "Перечисление COR_PRF_MODULE_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_MODULE_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_MODULE_FLAGS
helpviewer_keywords: COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 54a8ee366431360f7b653b48f4ce407a35f8465b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Модуль был загружен с диска.|  
|COR_PRF_MODULE_NGEN|Модуль, созданных генератором образов в машинном коде (Ngen.exe).|  
|COR_PRF_MODULE_DYNAMIC|Модуль был создан с методов в <xref:System.Reflection.Emit?displayProperty=nameWithType> пространства имен.|  
|COR_PRF_MODULE_COLLECTIBLE|Время жизни module осуществляется сборщиком мусора.|  
|COR_PRF_MODULE_RESOURCE|Модуль содержит без метаданных и используются исключительно как ресурс. Управляемый эквивалент этот бит — <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> метод.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Структура полей модуля в памяти является плоским, не сопоставлен. Если модуль этот бит задан, профилировщики, считывающие сведения непосредственно из заголовок переносимого исполняемого (PE) файла, необходимо будет соблюдать осторожность при интерпретации относительные виртуальные адреса (RVA) в заголовке.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|В метаданных для сборки этот модуль установлен флаг содержимого типа среды выполнения Windows. Это справедливо для всех модулей метаданных Windows (.winmd).|  
  
## <a name="remarks"></a>Примечания  
 Биты в COR_PRF_MODULE_FLAGS возвращаются профилировщику в `pdwModuleFlags` выходной параметр [ICorProfilerInfo3::GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) метод. Возможны некоторые сочетания двух или более флагов, но не все комбинации возможны.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
