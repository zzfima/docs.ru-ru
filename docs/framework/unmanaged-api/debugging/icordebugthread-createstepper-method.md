---
title: "Метод ICorDebugThread::CreateStepper"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b66c3e536104a46b65c92fe038fb5a92d79db299
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreatestepper-method"></a>Метод ICorDebugThread::CreateStepper
Создает объект, позволяющий проходить через активного кадра ICorDebugThread ICorDebugStepper.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppStepper`  
 [out] Указатель на адрес `ICorDebugStepper` объектом, который позволяет проходить через активный кадр для данного потока.  
  
## <a name="remarks"></a>Примечания  
 Возможно, активного кадра неуправляемого кода.  
  
 `ICorDebugStepper` Интерфейса необходимо использовать для фактического пошагового выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
