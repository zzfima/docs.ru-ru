---
title: Метод ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754855"
---
# <a name="icordebugframegetstackrange-method"></a>Метод ICorDebugFrame::GetStackRange
Возвращает диапазон абсолютных адресов этого кадра стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pStart`  
 [out] Указатель на `CORDB_ADDRESS` , указывающий начальный адрес кадра стека, представленный этим `ICorDebugFrame` объекта.  
  
 `pEnd`  
 [out] Указатель на `CORDB_ADDRESS` , указывающий конечный адрес кадра стека, представленный этим `ICorDebugFrame` объекта.  
  
## <a name="remarks"></a>Примечания  
 Диапазон адресов стека полезно для соединения вместе перемежаемых трассировок стека из нескольких обработчиков отладки. Числовой диапазон не предоставляет сведений о содержимом кадра стека. Он имеет смысл только для сравнения расположений кадра стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
