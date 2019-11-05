---
title: 'Метод ICorDebugVariableHome:: GetSlotIndex'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: dfc2e91599e7f05d90d56af07b71313e9eecaa51
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121052"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>Метод ICorDebugVariableHome:: GetSlotIndex
Возвращает управляемый индекс в виде слота локальной переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pSlotIndex`  
 заполняет Указатель на индекс в виде слота локальной переменной.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает следующие значения.  
  
|значения|Описание|  
|-----------|-----------------|  
|`S_OK`|Вызов метода вернул значение индекса слота в `pSlotIndex`.|  
|`E_FAIL`|Текущий экземпляр [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) представляет аргумент функции.|  
  
## <a name="remarks"></a>Заметки  
 Чтобы получить метаданные для этой локальной переменной, можно использовать индекс Slot.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
