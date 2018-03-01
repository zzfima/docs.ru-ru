---
title: "Метод ICorDebugNativeFrame::SetIP"
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
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25b4f42eb6f10ecade468824d9d790a2bce740a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframesetip-method"></a>Метод ICorDebugNativeFrame::SetIP
Задает указатель инструкций заданное расположение смещения в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `nOffset`  
 [in] Расположение смещения в машинном коде.  
  
## <a name="remarks"></a>Примечания  
 Вызовы `SetIP` немедленно сделать недействительными все фреймы и цепочки для текущего потока. Если отладчик сведениях о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) предпримет попытку сохранить кадр стека в допустимом состоянии. Тем не менее даже если кадр находится в допустимом состоянии, как среды выполнения, по-прежнему возможно проблемы, такие как неинициализированных локальных переменных и т. д. Вызывающий объект отвечает за обеспечение согласованности выполняемой программы.  
  
 На 64-разрядных платформах, не может быть перемещен указатель инструкций из `catch` или `finally` блока. Если `SetIP` вызывается для выполнения такого перемещения на 64-разрядной платформе, она возвратит значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
