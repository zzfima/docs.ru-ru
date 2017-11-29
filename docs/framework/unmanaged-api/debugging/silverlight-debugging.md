---
title: "Отладка в Silverlight"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf39d2dd12207d594c7bf5bd5b249d82c3f15d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="silverlight-debugging"></a>Отладка в Silverlight
В этом разделе описываются среда и интерфейсы, предоставляемые средой CLR для поддержки отладки приложений на основе Silverlight, работающих в ОС Windows или на платформе Macintosh.  
  
## <a name="in-this-section"></a>Содержание  
 [Функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 Предоставляет механизм для перечисления сред CLR в процессе.  
  
 [Функция CloseCLREnumeration](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 Закрывает все допустимые события продолжения запуска среды CLR, находятся в массиве дескрипторов, возвращенном [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)и освобождает память для массивов дескрипторов и строк пути.  
  
 [Функция CreateCoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
 [Функция CreateCordbObject](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 Создает интерфейс отладчика, обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.  
  
 [Функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 Создает строку версии из пути среды CLR в целевом процессе.  
  
 [Функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 Принимает строку версии среды CLR возвращается из [функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)функцией и возвращает соответствующий интерфейс отладчика.  
  
 [Структура CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 Представляет процесс, который выполняется на удаленном компьютере.  
  
 [Структура CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.  
  
 [Функция GetStartupNotificationEvent](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.  
  
 [Интерфейс ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
 [Функция InitDbgTransportManager](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
 [Функция ShutdownDbgTransportManager](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 Завершает работу диспетчера транспорта для подключения к удаленному целевому компьютеру.  
  
## <a name="see-also"></a>См. также  
 [Компонентные классы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
