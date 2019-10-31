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
ms.openlocfilehash: 5715f0634346dd0c6591cfe5687690aa0fba95f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125322"
---
# <a name="icordebugdatatargetgetplatform-method"></a>Метод ICorDebugDataTarget::GetPlatform
Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTargetPlatform`  
 заполняет Указатель на перечисление [кордебугплатформенум](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) , описывающее целевую платформу.  
  
## <a name="remarks"></a>Заметки  
 Возвращаемое значение перечисления `CorDebugPlatformEnum` используется интерфейсом [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) для определения сведений о целевом процессе, таких как размер указателя, макет адресного пространства, набор регистров, формат инструкций, контекстный макет и соглашения о вызовах.  
  
 Значение `pTargetPlatform` может ссылаться на платформу, которая эмулируется для целевого объекта, вместо того, чтобы указывать фактическое используемое оборудование. Например, процесс, выполняемый в среде Windows on Windows (WOW) в 64-разрядном выпуске операционной системы Windows, должен использовать `CORDB_PLATFORM_WINDOWS_X86` значение перечисления [кордебугплатформенум](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) .  
  
 Этот метод должен быть выполнен. В случае сбоя Целевая платформа будет непригодна для использования. Метод может завершиться ошибкой по следующим причинам:  
  
- Платформа, которая эмулируется для целевого объекта, непригодна для использования.  
  
- Фактическое оборудование на целевой платформе непригодно для использования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
