---
title: Метод ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1522d643a69c47eec03770a8f51756dd4250075a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309424"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Метод ICorDebugRegisterSet2::GetRegistersAvailable
Возвращает массив байтов, предоставляет битовую схему, доступных регистров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `numChunks`  
 [in] Размер массива `availableRegChunks`.  
  
 `availableRegChunks`  
 [out] Массив байтов, каждый бит соответствует регистру. Если регистр, устанавливается соответствующий бит в регистре.  
  
## <a name="remarks"></a>Примечания  
 Значения перечисления CorDebugRegister указывают регистры различных микропроцессоров. Старшие разряды пять каждому значению типа являются порядковым номером в `availableRegChunks` массив байтов. Нижние три бит каждого значения идентифицируют положение бита в индексируемом байте. Учитывая `CorDebugRegister` значение, указывающее определенный регистр, положение регистра в маске определяется следующим образом:  
  
1. Извлечь индекс, необходимые для доступа к правильный байта в `availableRegChunks` массива:  
  
     `CorDebugRegister` Значение >> 3  
  
2. Извлеките положение бита в индексированных байт, где нулевой бит — наименее значимым битом.  
  
     `CorDebugRegister` значение & 7  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [Интерфейс ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
