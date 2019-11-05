---
title: Метод ICorDebugILFrame::SetIP
ms.date: 03/30/2017
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
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095435"
---
# <a name="icordebugilframesetip-method"></a>Метод ICorDebugILFrame::SetIP
Задает указатель инструкции в указанном расположении смещения в коде промежуточного языка Майкрософт (MSIL).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nOffset`  
 Положение смещения в коде MSIL.  
  
## <a name="remarks"></a>Заметки  
 Вызовы `SetIP` немедленно делают недействительными все кадры и цепочки для текущего потока. Если отладчику требуются сведения о кадрах после вызова `SetIP`, он должен выполнить новую трассировку стека.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) попытается удержать кадр стека в допустимом состоянии. Тем не менее, даже если кадр находится в допустимом состоянии, могут возникнуть проблемы, например неинициализированные локальные переменные. Вызывающий объект отвечает за обеспечение согласованности выполняющейся программы.  
  
 На 64-разрядных платформах указатель инструкции не может быть перемещен из `catch` или `finally` блока. Если вызывается `SetIP`, чтобы выполнить такое перемещение на 64-разрядной платформе, он возвратит значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
