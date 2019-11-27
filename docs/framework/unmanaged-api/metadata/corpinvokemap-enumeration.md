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
ms.openlocfilehash: 17b7af7016cf88fd3ae263dd952502d515b0c833
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441556"
---
# <a name="corpinvokemap-enumeration"></a>Перечисление CorPinvokeMap
Задает параметры для вызова PInvoke.  
  
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
  
|Член|Описание|  
|------------|-----------------|  
|`pmNoMangle`|Используйте каждое имя элемента, как указано.|  
|`pmCharSetMask`|Зарезервировано.|  
|`pmCharSetNotSpec`|Зарезервировано.|  
|`pmCharSetAnsi`|Маршалирует строки как многобайтовые символьные строки.|  
|`pmCharSetUnicode`|Маршалирует строки в виде 2-байтовых символов Юникода.|  
|`pmCharSetAuto`|Автоматически маршалировать строки в соответствии с целевой операционной системой. По умолчанию используется Юникод в Windows NT, Windows 2000, Windows XP и семействе Windows Server 2003. значение по умолчанию — ANSI в Windows 98 и Windows Me.|  
|`pmBestFitUseAssem`|Зарезервировано.|  
|`pmBestFitEnabled`|Выполните наилучшее сопоставление символов Юникода, не имея точного соответствия в кодировке ANSI.|  
|`pmBestFitDisabled`|Не выполняйте наилучшее соответствие символов Юникода. В этом случае все несопоставимые символы будут заменены символом "?".|  
|`pmBestFitMask`|Зарезервировано.|  
|`pmThrowOnUnmappableCharUseAssem`|Зарезервировано.|  
|`pmThrowOnUnmappableCharEnabled`|Создавать исключение, когда модуль маршалинга взаимодействия встречает несопоставимый символ.|  
|`pmThrowOnUnmappableCharDisabled`|Не вызывайте исключение, если модуль маршалинга взаимодействия встречает несопоставимый символ.|  
|`pmThrowOnUnmappableCharMask`|Зарезервированное|  
|`pmSupportsLastError`|Разрешить вызываемому методу вызывать функцию Win32 `SetLastError` перед возвратом из метода с атрибутом.|  
|`pmCallConvMask`|Зарезервированное|  
|`pmCallConvWinapi`|Используйте соглашение о вызовах платформы по умолчанию. Например, в Windows значение по умолчанию — `StdCall`, а Windows CE .NET — `Cdecl`.|  
|`pmCallConvCdecl`|Используйте соглашение о вызовах `Cdecl`. В этом случае вызывающий объект очищает стек. Это позволяет вызывать функции с `varargs` (то есть с функциями, принимающими переменное количество параметров).|  
|`pmCallConvStdcall`|Используйте соглашение о вызовах `StdCall`. В этом случае вызываемый объект очищает стек. Это соглашение по умолчанию для вызова неуправляемых функций с помощью вызова неуправляемого кода.|  
|`pmCallConvThiscall`|Используйте соглашение о вызовах `ThisCall`. В этом случае первый параметр является указателем `this` и хранится в регистре ECX. Другие параметры помещаются в стек. Соглашение о вызовах `ThisCall` используется для вызова методов для классов, экспортируемых из неуправляемой библиотеки DLL.|  
|`pmCallConvFastcall`|Зарезервировано.|  
|`pmMaxValue`|Зарезервировано.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
