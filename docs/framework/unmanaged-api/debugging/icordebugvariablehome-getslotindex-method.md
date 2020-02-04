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
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790973"
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
  
|{2&gt;Value&lt;2}|Описание|  
|-----------|-----------------|  
|`S_OK`|Вызов метода вернул значение индекса слота в `pSlotIndex`.|  
|`E_FAIL`|Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет аргумент функции.|  
  
## <a name="remarks"></a>Заметки  
 Чтобы получить метаданные для этой локальной переменной, можно использовать индекс Slot.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
