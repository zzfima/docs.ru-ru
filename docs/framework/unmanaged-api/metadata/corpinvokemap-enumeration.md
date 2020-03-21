---
title: Перечисление CorPinvokeMap
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176153"
---
# <a name="corpinvokemap-enumeration"></a>Перечисление CorPinvokeMap
Определяет варианты вызова PInvoke.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`pmNoMangle`|Используйте каждое имя участника в качестве указанного.|  
|`pmCharSetMask`|Зарезервировано.|  
|`pmCharSetNotSpec`|Зарезервировано.|  
|`pmCharSetAnsi`|Маршалирует строки в виде строк многобайтовых символов.|  
|`pmCharSetUnicode`|Маршалирует строки в виде 2-байтных символов Юникода.|  
|`pmCharSetAuto`|Выполняет автоматический маршалинг строк способом, соответствующим целевой операционной системе. По умолчанию по умолчанию находится Unicode на Windows NT, Windows 2000, Windows XP и семейство Windows Server 2003; по умолчанию ANSI на Windows 98 и Windows Me.|  
|`pmBestFitUseAssem`|Зарезервировано.|  
|`pmBestFitEnabled`|Выполняйте наиболее подходящее отображение символов Unicode, которым не хватает точного соответствия в наборе символов ANSI.|  
|`pmBestFitDisabled`|Не выполняйте наиболее оптимальное отображение символов Unicode. В этом случае все неприязненное символы будут заменены на '?'.|  
|`pmBestFitMask`|Зарезервировано.|  
|`pmThrowOnUnmappableCharUseAssem`|Зарезервировано.|  
|`pmThrowOnUnmappableCharEnabled`|Бросьте исключение, когда interop marshaler сталкивается с непомерным характером.|  
|`pmThrowOnUnmappableCharDisabled`|Не бросайте исключение, когда интероп маршалер сталкивается с непомерным персонажем.|  
|`pmThrowOnUnmappableCharMask`|Reserved|  
|`pmSupportsLastError`|Разрешить вызывающего вызова функции `SetLastError` Win32, прежде чем вернуться из приписываемого метода.|  
|`pmCallConvMask`|Reserved|  
|`pmCallConvWinapi`|Используйте конвенцию вызова платформы по умолчанию. Например, на Windows `StdCall` по умолчанию и на `Cdecl`Windows CE .NET это .|  
|`pmCallConvCdecl`|Используйте `Cdecl` конвенцию о вызове. В этом случае абонент очищает стек. Это позволяет вызывать функции с (т.е. `varargs` функциями, которые принимают переменное количество параметров).|  
|`pmCallConvStdcall`|Используйте `StdCall` конвенцию о вызове. В этом случае звонивший очищает стек. Это соглашение, используемое по умолчанию для вызова неуправляемых функций с вызовом неуправляемого кода.|  
|`pmCallConvThiscall`|Используйте `ThisCall` конвенцию о вызове. В этом случае первым параметром является `this` указатель и хранится в регистре ECX. Другие параметры помещаются в стек. Конвенция `ThisCall` вызова используется для вызова методов на классах, экспортированных из неуправляемого DLL.|  
|`pmCallConvFastcall`|Зарезервировано.|  
|`pmMaxValue`|Зарезервировано.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
