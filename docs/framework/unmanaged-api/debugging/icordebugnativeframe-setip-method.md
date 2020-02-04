---
title: Метод ICorDebugNativeFrame::SetIP
ms.date: 03/30/2017
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
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792783"
---
# <a name="icordebugnativeframesetip-method"></a>Метод ICorDebugNativeFrame::SetIP
Задает указатель инструкции в указанном расположении смещения в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nOffset`  
 окне Положение смещения в машинном коде.  
  
## <a name="remarks"></a>Заметки  
 Вызовы `SetIP` немедленно делают недействительными все кадры и цепочки для текущего потока. Если отладчику требуются сведения о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.  
  
 [ICorDebug](icordebug-interface.md) попытается удержать кадр стека в допустимом состоянии. Однако даже если кадр находится в допустимом состоянии, то, что касается среды выполнения, могут возникнуть проблемы, например неинициализированные локальные переменные и т. д. Вызывающий объект отвечает за выполнение согласованности выполняющейся программы.  
  
 На 64-разрядных платформах указатель инструкции не может быть перемещен из `catch` или `finally` блока. Если вызывается `SetIP`, чтобы выполнить такое перемещение на 64-разрядной платформе, он возвратит значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:
