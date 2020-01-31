---
title: Метод ICorDebugCode::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777888"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>Метод ICorDebugCode::GetILToNativeMapping
Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления из смещений MSIL к собственным смещениям.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cMap`  
 [in] Размер массива `map`.  
  
 `pcMap`  
 заполняет Указатель на фактическое число элементов, возвращаемых в массиве `map`.  
  
 `map`  
 заполняет Массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`, каждый из которых представляет сопоставление смещения MSIL со смещением в машинном коде.  
  
 Порядок для массива возвращаемых элементов отсутствует.  
  
## <a name="remarks"></a>Заметки  
 Метод `GetILToNativeMapping` возвращает значимые результаты только в том случае, если этот экземпляр "ICorDebugCode" представляет машинный код, который был JIT-скомпилирован из кода MSIL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugCode](icordebugcode-interface1.md)
