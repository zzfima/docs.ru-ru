---
title: Метод ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 120a970aac33b1ab06ae47335a959d2791f893ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178980"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a>Метод ICorDebugDataTarget2::EnumerateThreadIDs
Возвращает список идентификаторов активных потоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 cThreadIDs  
 [входной] Максимальное число потоков, идентификаторы которых могут быть возвращены.  
  
 pcThreadIds  
 [выходной] Указатель на `ULONG32`, который указывает фактическое количество идентификаторов потоков, записанных в массив `pThreadIds`.  
  
 pThreadIDs  
 Массив идентификаторов потоков.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md). **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
