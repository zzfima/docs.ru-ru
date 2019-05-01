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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045400"
---
# <a name="corpinvokemap-enumeration"></a>Перечисление CorPinvokeMap
Указывает параметры для вызова PInvoke.  
  
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
  
|Член|Описание|  
|------------|-----------------|  
|`pmNoMangle`|Используйте указанные имя каждого элемента.|  
|`pmCharSetMask`|Зарезервировано.|  
|`pmCharSetNotSpec`|Зарезервировано.|  
|`pmCharSetAnsi`|Маршалирует строки в виде строки многобайтовых символов.|  
|`pmCharSetUnicode`|Маршалирует строки в виде 2-байтных символов Юникода.|  
|`pmCharSetAuto`|Выполняет автоматический маршалинг строк способом, соответствующим целевой операционной системы. По умолчанию используется Юникод для Windows NT, Windows 2000, Windows XP и семействе Windows Server 2003; по умолчанию используется ANSI для Windows 98 и Windows Me.|  
|`pmBestFitUseAssem`|Зарезервировано.|  
|`pmBestFitEnabled`|Выполните наилучшего сопоставления символов Юникода, не хватает точного совпадения в кодировку ANSI.|  
|`pmBestFitDisabled`|Не выполняйте наилучшего сопоставления символов Юникода. В этом случае всех неотображаемых символов будут заменены "?".|  
|`pmBestFitMask`|Зарезервировано.|  
|`pmThrowOnUnmappableCharUseAssem`|Зарезервировано.|  
|`pmThrowOnUnmappableCharEnabled`|Исключение при обнаружении маршалером взаимодействия несопоставимого символа.|  
|`pmThrowOnUnmappableCharDisabled`|Не следует генерировать исключения при обнаружении маршалером взаимодействия несопоставимого символа.|  
|`pmThrowOnUnmappableCharMask`|Зарезервированное|  
|`pmSupportsLastError`|Разрешить вызываемый объект для вызова Win32 `SetLastError` функции перед возвратом из метода с атрибутами.|  
|`pmCallConvMask`|Зарезервированное|  
|`pmCallConvWinapi`|Используйте соглашение о вызове платформы по умолчанию. Например, в Windows по умолчанию используется `StdCall` и на Windows CE .NET, это `Cdecl`.|  
|`pmCallConvCdecl`|Используйте `Cdecl` соглашение о вызовах. В этом случае вызывающий объект очищает стек. Это позволяет вызывать функции с `varargs` (то есть функции, которые принимают переменное количество параметров).|  
|`pmCallConvStdcall`|Используйте `StdCall` соглашение о вызовах. В этом случае вызываемый объект очищает стек. Это соглашение по умолчанию для вызова неуправляемых функций с вызовом неуправляемого кода.|  
|`pmCallConvThiscall`|Используйте `ThisCall` соглашение о вызовах. В этом случае первый параметр является `this` указатель и хранится в регистре ECX. Другие параметры помещаются в стек. `ThisCall` Соглашения о вызове используется для вызова методов в классах, экспортируемых из неуправляемой библиотеки DLL.|  
|`pmCallConvFastcall`|Зарезервировано.|  
|`pmMaxValue`|Зарезервировано.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
