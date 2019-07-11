---
title: Метод ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc647805fcb7d8354a2540ac9424dc7155853444
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745033"
---
# <a name="icordebugchainenumerateframes-method"></a>Метод ICorDebugChain::EnumerateFrames
Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppFrames`  
 [out] Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.  
  
## <a name="remarks"></a>Примечания  
 Цепь представляет физический стек вызова для потока.  
  
 `EnumerateFrames` Метод должен вызываться только для управляемых цепочек. API отладки не поддерживает методы для получения кадров, содержащихся в неуправляемых цепочки. Отладчик должен использовать другие средства для получения этих сведений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
