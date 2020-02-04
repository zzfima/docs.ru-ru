---
title: Метод ICorDebugDataTarget::GetPlatform
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: 3654c94975d16e35d5c3d8e762730d17509a2c6d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788877"
---
# <a name="icordebugdatatargetgetplatform-method"></a>Метод ICorDebugDataTarget::GetPlatform
Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTargetPlatform`  
 заполняет Указатель на перечисление [кордебугплатформенум](cordebugplatform-enumeration.md) , описывающее целевую платформу.  
  
## <a name="remarks"></a>Заметки  
 Возвращаемое значение перечисления `CorDebugPlatformEnum` используется интерфейсом [ICorDebug](icordebug-interface.md) для определения сведений о целевом процессе, таких как размер указателя, макет адресного пространства, набор регистров, формат инструкций, контекстный макет и соглашения о вызовах.  
  
 Значение `pTargetPlatform` может ссылаться на платформу, которая эмулируется для целевого объекта, вместо того, чтобы указывать фактическое используемое оборудование. Например, процесс, выполняемый в среде Windows on Windows (WOW) в 64-разрядном выпуске операционной системы Windows, должен использовать `CORDB_PLATFORM_WINDOWS_X86` значение перечисления [кордебугплатформенум](cordebugplatform-enumeration.md) .  
  
 Этот метод должен быть выполнен. В случае сбоя Целевая платформа будет непригодна для использования. Метод может завершиться ошибкой по следующим причинам:  
  
- Платформа, которая эмулируется для целевого объекта, непригодна для использования.  
  
- Фактическое оборудование на целевой платформе непригодно для использования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
