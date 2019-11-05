---
title: Интерфейс ICorDebugILFrame4
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 010d73309ae21f9a593f72533691bdd95fbd4132
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130851"
---
# <a name="icordebugilframe4-interface"></a>Интерфейс ICorDebugILFrame4
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|Возвращает список локальных переменных, доступных в текущем кадре.|  
|[Метод GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|Возвращает код, который выполняется этим кадром стека.|  
|[Метод GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|Возвращает значение локальной переменной в кадре промежуточного языка.|  
  
## <a name="remarks"></a>Заметки  
 Эти методы предоставляют функциональные возможности в дополнение к [возможностям,](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)предоставляемым методами [енумерателокалвариаблес](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [жетлокалвариабле](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) и. Каждый метод включает параметр `flags`, определяющий видимость дополнительных локальных переменных или кода, определенных ReJIT-запросом профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
