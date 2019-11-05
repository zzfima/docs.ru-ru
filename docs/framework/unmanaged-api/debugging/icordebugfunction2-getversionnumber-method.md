---
title: Метод ICorDebugFunction2::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 5826297d8151cf05e1ec08acbf5c9cd381d2452b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137807"
---
# <a name="icordebugfunction2getversionnumber-method"></a>Метод ICorDebugFunction2::GetVersionNumber
Возвращает версию функции "изменить и продолжить".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pnVersion`  
 заполняет Указатель на целое число, представляющее номер версии функции, представленной этим объектом ICorDebugFunction2.  
  
## <a name="remarks"></a>Заметки  
 Среда выполнения отслеживает количество изменений, выполненных в каждом модуле во время сеанса отладки. Номер версии функции — это значение, превышающее число изменений, введенных в функцию. Исходной версией функции является версия 1. Число увеличивается для модуля каждый раз, когда для этого модуля вызывается [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) . Таким словами, если тело функции было заменено в первом и третьем вызове `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` может возвращать версию 1, 2 или 4 для этой функции, но не версию 3. (Эта функция не имеет версии 3.)  
  
 Номер версии ведется отдельно для каждого модуля. Поэтому при выполнении четырех изменений в модуле 1 и отсутствии в модуле 2 при следующем редактировании в модуле 1 будет присвоен номер версии 6 всем измененным функциям в модуле 1. Если одно и то же изменение касается модуля 2, функции в модуле 2 будут получать номер версии 2.  
  
 Номер версии, полученный методом `GetVersionNumber`, может быть меньше, чем получает метод [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 Метод [ICorDebugCode:: жетверсионнумбер](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) выполняет ту же операцию, что и `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
