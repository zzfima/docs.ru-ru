---
title: Интерфейс ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131892"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>Интерфейс ICorDebugRuntimeUnwindableFrame
Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
## <a name="remarks"></a>Заметки  
 `ICorDebugRuntimeUnwindableFrame` является специализированной версией интерфейса ICorDebugFrame. Он используется неуправляемыми методами, требующими от среды выполнения очистки кадра в текущем стеке. Существующие правила очистки не работают, так как они не используют JIT-скомпилированный код. Когда отладчик видит неотображаемый кадр, он должен использовать метод [икордебугстакквалк:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) для его очистки, но должен выполнить проверку. Когда отладчик получает `ICorDebugRuntimeUnwindableFrame`, он может вызвать метод [икордебугстакквалк:: oncontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) для получения контекста кадра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
