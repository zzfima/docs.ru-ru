---
title: Метод ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 967c0e18b354e6e1cd0d87900e3cde85991c0862
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794328"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>Метод ICorDebugInternalFrame2::GetFrameAddress
Возвращает адрес стека внутреннего кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAddress`  
 заполняет Указатель на `CORDB_ADDRESS` для внутреннего кадра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Адрес внутреннего кадра успешно возвращен.|  
|E_FAIL|Не удалось вернуть адрес внутреннего кадра.|  
|E_INVALIDARG|Параметр `pAddress` имеет значение `null`.|  
  
## <a name="remarks"></a>Заметки  
 Значение, возвращаемое в `pAddress`, можно использовать для определения расположения внутреннего кадра относительно других кадров в стеке. Даже на компьютерах на базе IA-64 внутренний кадр находится только в стеке и не имеет соответствующего указателя на резервное хранилище.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
