---
title: Метод ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89182739633984011aaab3d7900d376b6db5ef99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987193"
---
# <a name="icordebugthreadcreatestepper-method"></a>Метод ICorDebugThread::CreateStepper
Создает объект, позволяющий пошаговое выполнение активного кадра ICorDebugThread ICorDebugStepper.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppStepper`  
 [out] Указатель на адрес `ICorDebugStepper` объект, который позволяет пошаговое выполнение активного кадра для данного потока.  
  
## <a name="remarks"></a>Примечания  
 Возможно, активного кадра неуправляемого кода.  
  
 `ICorDebugStepper` Интерфейс необходимо использовать для фактического пошагового выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
