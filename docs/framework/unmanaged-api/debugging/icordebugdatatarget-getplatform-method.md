---
title: "Метод ICorDebugDataTarget::GetPlatform"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetPlatform Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf2f852d0da36211e379a4068cccff9dfc656100
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetplatform-method"></a>Метод ICorDebugDataTarget::GetPlatform
Предоставляет сведения о платформе, включая архитектуру процессора и операционной системы, на котором выполняется целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pTargetPlatform`  
 [out] Указатель на [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) перечисление, описывающее целевой платформы.  
  
## <a name="remarks"></a>Примечания  
 `CorDebugPlatformEnum` Возвращаемое значение перечисления используется [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс для определения сведений целевого процесса, такие как его размер указателя, структура адресного пространства, набор регистров, формат команд, структура контекста и соглашения о вызовах.  
  
 `pTargetPlatform` Может указывать на платформу, эмулируется для целевого объекта вместо указания фактическое оборудование используется. Например, следует использовать процесс, который выполняется в Windows в среде Windows (WOW) в 64-разрядной версии операционной системы Windows `CORDB_PLATFORM_WINDOWS_X86` значение [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) перечисления.  
  
 Этот метод должен завершиться успешно. В случае неудачи целевая платформа не может использоваться. Метод может завершиться ошибкой по следующим причинам:  
  
-   Платформы, которая эмулируется для целевого объекта не может использоваться.  
  
-   Фактические аппаратные средства целевой платформы не может использоваться.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorDebugDataTarget-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
