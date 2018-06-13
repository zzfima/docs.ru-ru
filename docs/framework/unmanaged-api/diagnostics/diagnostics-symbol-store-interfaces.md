---
title: Интерфейсы хранилища символов диагностики
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435816"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Интерфейсы хранилища символов диагностики
В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору генерировать символьную информацию для использования отладчиком.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Интерфейс IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Предоставляет методы для отображения текущих привязки сведений о выполняемом приложении.  
  
 [Интерфейс IDebugAutoAttach](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Определяет интерфейс для вызываемого сервером автоматического вложения отладчика.  
  
 [Интерфейс INotifyConnection2](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Объявляет методы для регистрации и отмены регистрации источника уведомления соединения.  
  
 [Интерфейс INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Объявляет методы для уведомления приемника.  
  
 [Интерфейс INotifySource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Объявляет метод для установки фильтров оповещения.  
  
 [Интерфейс ISymENCUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Предоставляет сведения для "Изменить и продолжить".  
  
 [Интерфейс ISymUnmanagedAsyncMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Этот интерфейс является дополнением к чтения [интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Разрешает определение сведений о методе необязательный асинхронный метод символ. Необходимо использовать открытый метод (то есть, между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).  
  
 [Интерфейс ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Представляет модуль привязки символов для неуправляемого кода.  
  
 [Интерфейс ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Представляет модуль привязки символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейса.  
  
 [Интерфейс ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Представляет модуль привязки символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейса.  
  
 [Интерфейс ISymUnmanagedConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Предоставляет доступ к неуправляемым константам.  
  
 [Интерфейс ISymUnmanagedDispose](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Освобождает неуправляемые ресурсы.  
  
 [Интерфейс ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Представляет документ, на который ссылается хранилище символов.  
  
 [Интерфейс ISymUnmanagedDocumentWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Предоставляет методы для записи в документ, на который ссылается хранилище символов.  
  
 [Интерфейс ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Предоставляет методы для "Изменить и продолжить".  
  
 [Интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Представляет метод в хранилище символов.  
  
 [Интерфейс ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Представляет пространство имен.  
  
 [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.  
  
 [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Получает метод средства чтения символов, получив токен метода и номеру версии редактирования и копирования.  
  
 [Интерфейс ISymUnmanagedReaderSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Предоставляет методы, получающие сведения о поиске символов.  
  
 [Интерфейс ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Представляет лексическую область видимости в пределах одного метода.  
  
 [Интерфейс ISymUnmanagedScope2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Представляет лексическую область в методе и расширяет `ISymUnmanagedScope` интерфейс с методами, которые получают сведения о константы, определенные в области...  
  
 [Интерфейс ISymUnmanagedSourceServerModule](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Предоставляет данные сервера источника для модуля.  
  
 [Интерфейс ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Предоставляет методы, получающие сведения о пути поиска.  
  
 [Интерфейс ISymUnmanagedVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Представляет переменную, например параметр, локальную переменную или поле.  
  
 [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.  
  
 [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные. Расширяет `ISymUnmanagedWriter` интерфейса.  
  
 [Интерфейс ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные. Расширяет `ISymUnmanagedWriter` интерфейса.  
  
 [Интерфейс ISymUnmanagedWriter4](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 Интерфейс ISymUnmanagedWriter4.  
  
 [Интерфейс ISymUnmanagedWriter5](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 Интерфейс ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Перечисления хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Структуры хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
