---
title: Метод ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792807"
---
# <a name="icordebugnativeframecansetip-method"></a>Метод ICorDebugNativeFrame::CanSetIP
Возвращает значение HRESULT, указывающее, можно ли задать для указателя инструкций (IP) заданное положение смещения в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nOffset`  
 окне Требуемый параметр для указателя инструкции.  
  
## <a name="remarks"></a>Заметки  
 Перед вызовом метода [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) используйте метод `CanSetIP`. Если `CanSetIP` возвращает любое значение HRESULT, отличное от S_OK, вы по-прежнему можете вызывать `ICorDebugNativeFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит безопасность и правильное выполнение отлаживаемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:
