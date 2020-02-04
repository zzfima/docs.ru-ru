---
title: Интерфейс ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: fa31b8a6cc96935319e9bef3e561790b65e33a87
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777590"
---
# <a name="icordebugheapvalue-interface"></a>Интерфейс ICorDebugHeapValue

Подкласс "ICorDebugValue", представляющий объект, собранный сборщиком мусора среды CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateRelocBreakpoint](icordebugheapvalue-createrelocbreakpoint-method.md)|Не реализовано.|  
|[Метод IsValid](icordebugheapvalue-isvalid-method.md)|Возвращает значение, указывающее, является ли допустимым объект, представленный данным `ICorDebugHeapValue`, или освобожден сборщиком мусора. Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.|  
  
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
