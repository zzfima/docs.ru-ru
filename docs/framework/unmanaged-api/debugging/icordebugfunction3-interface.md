---
title: Интерфейс ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3eebdf56796fe599ec6ff62d7008d1af3be796e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926836"
---
# <a name="icordebugfunction3-interface"></a>Интерфейс ICorDebugFunction3
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Логически расширяет интерфейс ICorDebugFunction, чтобы предоставить доступ к коду из запроса ReJIT.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetActiveReJitRequestILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|Возвращает указатель интерфейса на [икордебугилкоде](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [ReJIT Руководство](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
