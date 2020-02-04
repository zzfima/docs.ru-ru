---
title: Интерфейс ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793633"
---
# <a name="iclrdebugging-interface"></a>Интерфейс ICLRDebugging
Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)|Возвращает интерфейс "ICorDebugProcess", соответствующий модулю среды CLR, загруженному в процессе.|  
|[Метод CanUnloadNow](iclrdebugging-canunloadnow-method.md)|Определяет, используется ли по-прежнему Библиотека, предоставленная интерфейсом [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) , или она может быть выгружена.|  
  
## <a name="remarks"></a>Заметки  
 Экземпляр интерфейса `ICLRDebugging` можно получить с помощью функции [клркреатеинстанце](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
