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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e2edc64cd9067ed89ae0e309c6a5630319ce835
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420603"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>Интерфейс ICorDebugRuntimeUnwindableFrame
Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugRuntimeUnwindableFrame` является специальной версией оператора ICorDebugFrame-интерфейс. Он используется неуправляемых методов, которым требуется среда выполнения для раскручивания кадра текущего стека. Существующие соглашения по раскрутке не работают, так как они не используют JIT-скомпилированный код. Когда отладчик видит удаляемых кадр, следует использовать [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) метод, чтобы развернуть его, но его проверку должен выполнять самостоятельно. Когда отладчик получает `ICorDebugRuntimeUnwindableFrame`, он может вызвать [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) метод для извлечения контекста кадра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
