---
title: "Перечисление CorPinvokeMap"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e0771ce54e7e2973525bfcf4aba4c1f7ddf0a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corpinvokemap-enumeration"></a>Перечисление CorPinvokeMap
Задает параметры для вызова PInvoke.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`pmNoMangle`|Используйте имя каждого элемента, как указано.|  
|`pmCharSetMask`|Зарезервировано.|  
|`pmCharSetNotSpec`|Зарезервировано.|  
|`pmCharSetAnsi`|Маршалинг строк как строки многобайтовых символов.|  
|`pmCharSetUnicode`|Маршалинг строк как 2-байтовые символы Юникода.|  
|`pmCharSetAuto`|Выполняет автоматический маршалинг строк, соответствующую целевой операционной системы. Значение по умолчанию — Юникод в Windows NT, Windows 2000, Windows XP и семейства Windows Server 2003; значение по умолчанию — ANSI для Windows 98 и Windows Me.|  
|`pmBestFitUseAssem`|Зарезервировано.|  
|`pmBestFitEnabled`|Выполните наилучшего сопоставления символов Юникода, в которых не хватает точного совпадения в наборе символов ANSI.|  
|`pmBestFitDisabled`|Не выполняйте наилучшего сопоставления символов Юникода. В этом случае всех неотображаемых символов будут заменены "?".|  
|`pmBestFitMask`|Зарезервировано.|  
|`pmThrowOnUnmappableCharUseAssem`|Зарезервировано.|  
|`pmThrowOnUnmappableCharEnabled`|Выдает исключение при обнаружении упаковщик взаимодействия несопоставимого символа.|  
|`pmThrowOnUnmappableCharDisabled`|Вызывает исключение при обнаружении упаковщик взаимодействия несопоставимого символа.|  
|`pmThrowOnUnmappableCharMask`|Зарезервированное|  
|`pmSupportsLastError`|Разрешить вызываемому вызывать Win32 `SetLastError` функции перед возвратом из метода, использующего атрибуты.|  
|`pmCallConvMask`|Зарезервированное|  
|`pmCallConvWinapi`|Используйте соглашение о вызовах платформы по умолчанию. Например, в Windows по умолчанию используется `StdCall` и в Windows CE .NET является `Cdecl`.|  
|`pmCallConvCdecl`|Используйте `Cdecl` соглашение о вызовах. В этом случае вызывающий объект очищает стек. Это позволяет вызывать функции с `varargs` (функций, принимающих переменное количество параметров).|  
|`pmCallConvStdcall`|Используйте `StdCall` соглашение о вызовах. В этом случае вызываемый метод очищает стек. Это соглашение по умолчанию для вызова неуправляемых функций с вызовом неуправляемого кода.|  
|`pmCallConvThiscall`|Используйте `ThisCall` соглашение о вызовах. В этом случае первый параметр — `this` указателя и хранится в регистре ECX. Другие параметры помещаются в стек. `ThisCall` Соглашение о вызовах используется для вызова методов в классах, экспортированных из неуправляемой библиотеки DLL.|  
|`pmCallConvFastcall`|Зарезервировано.|  
|`pmMaxValue`|Зарезервировано.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
