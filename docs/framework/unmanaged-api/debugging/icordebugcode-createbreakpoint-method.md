---
title: Метод ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d193f9aa4d051baa73944545d28a455495aeda40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185774"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>Метод ICorDebugCode::CreateBreakpoint
Создает точку останова в этом сегменте кода, начиная с указанной позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `offset`  
 [in] Смещение, с которой будет создана точка останова.  
  
 `ppBreakpoint`  
 [out] Указатель на адрес объекта «ICorDebugFunctionBreakpoint», который представляет точку останова.  
  
## <a name="remarks"></a>Примечания  
 Прежде чем точка останова не активна, его необходимо добавить в объект процесса.  
  
 Если этот код является код на промежуточном языке (MSIL), которая существует just-in-time (JIT)-компиляции, машинная версия кода, точка останова будет применяться в коде, а также JIT-компиляции. (То же самое значение true, если код является JIT-компиляции позже).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
