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
ms.openlocfilehash: 0e49c24a4b98a5287ec27b1667f45055d9a94d53
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903405"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>Метод ICorDebugCode::GetILToNativeMapping
Возвращает массив экземпляров «COR_DEBUG_IL_TO_NATIVE_MAP», которые представляют сопоставление из смещений промежуточного языка MSIL в собственные смещения.  
  
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
 [out] Массив `COR_DEBUG_IL_TO_NATIVE_MAP` структуры, каждый из которых представляет сопоставление смещение MSIL для смещения машинного кода.  
  
 Нет, не упорядочение массива возвращаемых элементов.  
  
## <a name="remarks"></a>Примечания  
 `GetILToNativeMapping` Метод возвращает значимые результаты только в том случае, если этот экземпляр «ICorDebugCode» представляет машинный код, который был just-in-time (JIT) скомпилированной на основе кода MSIL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс1 ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
