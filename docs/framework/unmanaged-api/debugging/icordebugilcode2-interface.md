---
title: Интерфейс ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: 30008d6cc98f7d0d0501d67e18703ed5a344d43a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794365"
---
# <a name="icordebugilcode2-interface"></a>Интерфейс ICorDebugILCode2
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Логически расширяет интерфейс [икордебугилкоде](icordebugilcode-interface.md) , чтобы предоставить методы, которые возвращают маркер для сигнатуры локальной переменной функции и сопоставляют смещенные промежуточные языки (IL) профилировщика с исходными смещениями Il метода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetInstrumentedILMap](icordebugilcode2-getinstrumentedilmap-method.md)|Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.|  
|[Метод GetLocalVarSigToken](icordebugilcode2-getlocalvarsigtoken-method.md)|Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
