---
title: Интерфейс ICorDebugAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784678"
---
# <a name="icordebugassembly-interface"></a>Интерфейс ICorDebugAssembly

Представляет сборку.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateModules](icordebugassembly-enumeratemodules-method.md)|Возвращает перечислитель для модулей, содержащихся в сборке.|  
|[Метод GetAppDomain](icordebugassembly-getappdomain-method.md)|Возвращает указатель интерфейса на домен приложения, содержащий данный `ICorDebugAssembly` экземпляр.|  
|[Метод GetCodeBase](icordebugassembly-getcodebase-method.md)|Не реализовано в текущей версии .NET Framework.|  
|[Метод GetName](icordebugassembly-getname-method.md)|Возвращает имя сборки.|  
|[Метод GetProcess](icordebugassembly-getprocess-method.md)|Возвращает экземпляр ICorDebugProcess, в котором выполняется сборка.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
