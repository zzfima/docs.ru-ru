---
title: Метод ICorDebugILFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: c6a02b080739d00667893008be4a19b4fa9a6ef2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788592"
---
# <a name="icordebugilframecansetip-method"></a>Метод ICorDebugILFrame::CanSetIP
Возвращает значение HRESULT, указывающее, безопасно ли устанавливать указатель инструкции в указанном расположении смещения в коде на языке MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nOffset`  
 окне Требуемый параметр для указателя инструкции.  
  
## <a name="remarks"></a>Заметки  
 Используйте метод `CanSetIP` перед вызовом метода [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) . Если `CanSetIP` возвращает любое значение HRESULT, отличное от S_OK, вы по-прежнему можете вызывать `ICorDebugILFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит безопасность и правильное выполнение отлаживаемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl, CorDebug, h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
