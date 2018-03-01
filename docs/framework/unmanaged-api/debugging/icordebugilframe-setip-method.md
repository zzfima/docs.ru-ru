---
title: "Метод ICorDebugILFrame::SetIP"
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
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: daffbbd9e961f4fdc7ff2e3c9be57e41e8fa3f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframesetip-method"></a>Метод ICorDebugILFrame::SetIP
Задает указатель инструкций заданное расположение смещения в код на промежуточном языке (MSIL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `nOffset`  
 Расположение смещения в MSIL-код.  
  
## <a name="remarks"></a>Примечания  
 Вызовы `SetIP` немедленно сделать недействительными все фреймы и цепочки для текущего потока. Если отладчик сведениях о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) предпримет попытку сохранить кадр стека в допустимом состоянии. Тем не менее даже если кадр находится в допустимом состоянии, по-прежнему возможно проблем, таких как неинициализированных локальных переменных. Вызывающий объект отвечает за обеспечение согласованности выполняемой программы.  
  
 На 64-разрядных платформах, не может быть перемещен указатель инструкций из `catch` или `finally` блока. Если `SetIP` вызывается для выполнения такого перемещения на 64-разрядной платформе, она возвратит значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
