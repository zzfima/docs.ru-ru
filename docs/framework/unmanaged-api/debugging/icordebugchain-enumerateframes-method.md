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
ms.openlocfilehash: 7568f8ca3b92ef465ab595348f68895f389d61e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645322"
---
# <a name="icordebugchainenumerateframes-method"></a>Метод ICorDebugChain::EnumerateFrames
Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
