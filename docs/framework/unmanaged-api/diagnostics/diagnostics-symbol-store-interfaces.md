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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787898"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="21c79-102">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="21c79-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="21c79-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору генерировать символьную информацию для использования отладчиком.</span><span class="sxs-lookup"><span data-stu-id="21c79-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21c79-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="21c79-104">In This Section</span></span>  
 [<span data-ttu-id="21c79-105">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="21c79-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="21c79-106">Предоставляет методы, которые отображают текущие привязки сведения о выполняющемся приложении.</span><span class="sxs-lookup"><span data-stu-id="21c79-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="21c79-107">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="21c79-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="21c79-108">Определяет интерфейс для вызываемого сервером автоматического вложения отладчика.</span><span class="sxs-lookup"><span data-stu-id="21c79-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="21c79-109">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="21c79-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="21c79-110">Объявляет методы для регистрации и отмены регистрации источника уведомления соединения.</span><span class="sxs-lookup"><span data-stu-id="21c79-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="21c79-111">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="21c79-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="21c79-112">Объявляет методы для уведомления приемника.</span><span class="sxs-lookup"><span data-stu-id="21c79-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="21c79-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="21c79-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="21c79-114">Объявляет метод для установки фильтров оповещения.</span><span class="sxs-lookup"><span data-stu-id="21c79-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="21c79-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="21c79-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="21c79-116">Предоставляет сведения для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="21c79-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="21c79-117">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="21c79-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="21c79-118">Этот интерфейс является дополнением к чтения [интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="21c79-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="21c79-119">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="21c79-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="21c79-120">Дает возможность определить сведения о методе необязательно асинхронный метод символ.</span><span class="sxs-lookup"><span data-stu-id="21c79-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="21c79-121">Необходимо использовать с помощью открытого метода (то есть между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="21c79-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="21c79-122">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="21c79-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="21c79-123">Представляет модуль привязки символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="21c79-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="21c79-124">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="21c79-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="21c79-125">Представляет модуль привязки символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="21c79-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="21c79-126">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="21c79-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="21c79-127">Представляет модуль привязки символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="21c79-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="21c79-128">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="21c79-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="21c79-129">Предоставляет доступ к неуправляемым константам.</span><span class="sxs-lookup"><span data-stu-id="21c79-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="21c79-130">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="21c79-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="21c79-131">Освобождает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="21c79-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="21c79-132">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="21c79-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="21c79-133">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="21c79-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="21c79-134">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="21c79-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="21c79-135">Предоставляет методы для записи в документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="21c79-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="21c79-136">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="21c79-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="21c79-137">Предоставляет методы для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="21c79-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="21c79-138">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="21c79-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="21c79-139">Представляет метод, в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="21c79-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="21c79-140">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="21c79-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="21c79-141">Представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="21c79-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="21c79-142">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="21c79-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="21c79-143">Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="21c79-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="21c79-144">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="21c79-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="21c79-145">Получает токен метода и номеру версии редактирования и копирования метода средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="21c79-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="21c79-146">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="21c79-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="21c79-147">Предоставляет методы, получающие сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="21c79-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="21c79-148">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="21c79-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="21c79-149">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="21c79-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="21c79-150">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="21c79-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="21c79-151">Представляет лексическую область в методе и расширяет `ISymUnmanagedScope` интерфейс с методами, которые получают сведения о константы, определенные в области...</span><span class="sxs-lookup"><span data-stu-id="21c79-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="21c79-152">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="21c79-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="21c79-153">Предоставляет данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="21c79-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="21c79-154">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="21c79-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="21c79-155">Предоставляет методы, которые получают сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="21c79-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="21c79-156">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="21c79-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="21c79-157">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="21c79-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="21c79-158">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="21c79-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="21c79-159">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="21c79-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="21c79-160">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="21c79-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="21c79-161">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="21c79-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="21c79-162">Расширяет `ISymUnmanagedWriter` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="21c79-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="21c79-163">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="21c79-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="21c79-164">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="21c79-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="21c79-165">Расширяет `ISymUnmanagedWriter` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="21c79-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="21c79-166">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="21c79-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="21c79-167">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="21c79-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="21c79-168">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="21c79-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="21c79-169">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="21c79-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="21c79-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="21c79-170">Related Sections</span></span>  
 [<span data-ttu-id="21c79-171">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="21c79-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="21c79-172">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="21c79-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="21c79-173">Отладка</span><span class="sxs-lookup"><span data-stu-id="21c79-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
