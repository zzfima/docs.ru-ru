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
ms.openlocfilehash: 1173091a5f2d8814747c93f827150afe39b8b309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcodecreatebreakpoint-method"></a>Метод ICorDebugCode::CreateBreakpoint
Создает точку останова в этом сегменте кода с указанным смещением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `offset`  
 [in] Позиция, с которого нужно создать точку останова.  
  
 `ppBreakpoint`  
 [out] Указатель на адрес объекта «ICorDebugFunctionBreakpoint», который представляет точку останова.  
  
## <a name="remarks"></a>Примечания  
 Перед активна, его необходимо добавить в объект процесса.  
  
 Если данный пример кода является код на промежуточном языке (MSIL), и нет just-in-time (JIT)-компиляции, машинная версия кода, точка останова будет применяться в JIT-скомпилированном коде. (То же самое значение true, если код является JIT-компиляции более поздней версии).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
