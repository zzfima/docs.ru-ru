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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426269d14992ae0f1f8c02619b259cfdd4bcbf8f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959441"
---
# <a name="icordebugassembly-interface"></a>Интерфейс ICorDebugAssembly

Представляет сборку.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Возвращает перечислитель для модулей, содержащихся в сборке.|  
|[Метод GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Возвращает указатель интерфейса на домен приложения, содержащий данный `ICorDebugAssembly` экземпляр.|  
|[Метод GetCodeBase](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|Не реализовано в текущей версии .NET Framework.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Возвращает имя сборки.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Возвращает экземпляр ICorDebugProcess, в котором выполняется сборка.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
