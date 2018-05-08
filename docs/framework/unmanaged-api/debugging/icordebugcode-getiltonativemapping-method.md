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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13ec60999db88b9d7191a3866fcebe8098b4edee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcodegetiltonativemapping-method"></a>Метод ICorDebugCode::GetILToNativeMapping
Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», представляющих сопоставление из смещений промежуточного языка MSIL в собственные смещения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cMap`  
 [in] Размер массива `map`.  
  
 `pcMap`  
 [out] Указатель на фактическое число элементов, возвращаемых в `map` массива.  
  
 `map`  
 [out] Массив `COR_DEBUG_IL_TO_NATIVE_MAP` структуры находящихся, каждый из которых представляет сопоставление смещение MSIL для смещения машинного кода.  
  
 Нет, не порядок элементов, возвращаемых в массив.  
  
## <a name="remarks"></a>Примечания  
 `GetILToNativeMapping` Метод возвращает значимые результаты только в том случае, если этот экземпляр «ICorDebugCode» представляет машинный код, который был just-in-time (JIT) компилируются в MSIL-код.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс1 ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
