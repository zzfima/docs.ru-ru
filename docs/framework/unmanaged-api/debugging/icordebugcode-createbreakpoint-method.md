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
ms.openlocfilehash: 1ec7d615b99ac301948d7ea25318115713ce06ea
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700845"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>Метод ICorDebugCode::CreateBreakpoint
Создает точку останова в этом сегменте кода в указанном смещении.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `offset`  
 окне Смещение для создания точки останова.  
  
 `ppBreakpoint`  
 заполняет Указатель на адрес объекта "ICorDebugFunctionBreakpoint", представляющего точку останова.  
  
## <a name="remarks"></a>Примечания  
 Прежде чем точка останова станет активной, ее необходимо добавить в объект Process.  
  
 Если этот код является кодом на языке MSIL и имеется JIT-скомпилированная собственная версия кода, то точка останова будет применена и в JIT-скомпилированном коде. (То же самое верно, если код компилируется позже.)  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
