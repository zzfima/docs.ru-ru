---
title: "Метод ICorDebugChain::EnumerateFrames"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a>Метод ICorDebugChain::EnumerateFrames
Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppFrames`  
 [out] Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.  
  
## <a name="remarks"></a>Примечания  
 Цепь представляет физический стек вызова для потока.  
  
 `EnumerateFrames` Метод должен вызываться только для управляемых цепочек. API отладки не предоставляет методы для получения кадров, содержащихся в неуправляемых цепочки. Отладчик должен использовать другие средства для получения этих сведений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
