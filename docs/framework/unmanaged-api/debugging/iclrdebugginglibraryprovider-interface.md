---
title: Интерфейс ICLRDebuggingLibraryProvider
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: a8d9348572ec0cf67c5facebb2053a7091661724
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793602"
---
# <a name="iclrdebugginglibraryprovider-interface"></a>Интерфейс ICLRDebuggingLibraryProvider
Включает метод [метода ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md)|Позволяет отладчику предоставлять обработчик для модуля, который можно использовать для загрузки библиотеки отладки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
