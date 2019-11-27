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
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448523"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Интерфейсы хранилища символов диагностики
В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору создавать символьные сведения для использования отладчиком.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Интерфейс IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Предоставляет методы, отображающие текущие сведения о привязке для выполняющегося приложения.  
  
 [Интерфейс IDebugAutoAttach](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Определяет интерфейс для автоматического присоединения отладчика, вызываемого сервером.  
  
 [Интерфейс INotifyConnection2](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Объявляет методы для регистрации и отмены регистрации источника уведомления о соединении.  
  
 [Интерфейс INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Объявляет методы для уведомления о приемнике.  
  
 [Интерфейс INotifySource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Объявляет метод для установки фильтров уведомлений.  
  
 [Интерфейс ISymENCUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Предоставляет сведения для функции "изменить и продолжить".  
  
 [Интерфейс ISymUnmanagedAsyncMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.  
  
 [Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Разрешает определение дополнительных сведений о асинхронном методе для каждого символа метода. Должен использовать с открытым методом (то есть между вызовами [метода опенмесод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)и [методом клосемесод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).  
  
 [Интерфейс ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Представляет связыватель символов для неуправляемого кода.  
  
 [Интерфейс ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Представляет связыватель символов для неуправляемого кода и расширяет интерфейс `ISymUnmanagedBinder`.  
  
 [Интерфейс ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Представляет связыватель символов для неуправляемого кода и расширяет интерфейс `ISymUnmanagedBinder`.  
  
 [Интерфейс ISymUnmanagedConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Предоставляет доступ к неуправляемым константам.  
  
 [Интерфейс ISymUnmanagedDispose](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Уничтожает неуправляемые ресурсы.  
  
 [Интерфейс ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Представляет документ, на который ссылается хранилище символов.  
  
 [Интерфейс ISymUnmanagedDocumentWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Предоставляет методы для записи в документ, на который ссылается хранилище символов.  
  
 [Интерфейс ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Предоставляет методы для функции "изменить и продолжить".  
  
 [Интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Представляет метод в хранилище символов.  
  
 [Интерфейс ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Представляет пространство имен.  
  
 [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Представляет средство чтения символов, предоставляющее доступ к документам, методам и переменным в хранилище символов.  
  
 [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Возвращает метод чтения символов по заданному токену метода и номеру версии для редактирования и копирования.  
  
 [Интерфейс ISymUnmanagedReaderSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Предоставляет методы, которые получают сведения о поиске символов.  
  
 [Интерфейс ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Представляет лексическую область внутри метода.  
  
 [Интерфейс ISymUnmanagedScope2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Представляет лексическую область внутри метода и расширяет интерфейс `ISymUnmanagedScope` с помощью методов, которые получают сведения о константах, определенных в области.  
  
 [Интерфейс ISymUnmanagedSourceServerModule](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Предоставляет данные сервера-источника для модуля.  
  
 [Интерфейс ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Предоставляет методы, получающие сведения о пути поиска.  
  
 [Интерфейс ISymUnmanagedVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Представляет переменную, например параметр, локальную переменную или поле.  
  
 [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.  
  
 [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных. Расширяет интерфейс `ISymUnmanagedWriter`.  
  
 [Интерфейс ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных. Расширяет интерфейс `ISymUnmanagedWriter`.  
  
 [Интерфейс ISymUnmanagedWriter4](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 Интерфейс ISymUnmanagedWriter4.  
  
 [Интерфейс ISymUnmanagedWriter5](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 Интерфейс ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Перечисления хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Структуры хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
