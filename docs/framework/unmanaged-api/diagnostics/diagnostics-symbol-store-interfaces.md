---
title: "Интерфейсы хранилища символов диагностики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a9550bf1e3e5500356584b1bdd53f5d3061e190
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="d1ce6-102">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d1ce6-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="d1ce6-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору генерировать символьную информацию для использования отладчиком.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1ce6-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d1ce6-104">In This Section</span></span>  
 [<span data-ttu-id="d1ce6-105">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="d1ce6-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="d1ce6-106">Предоставляет методы для отображения текущих привязки сведений о выполняемом приложении.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="d1ce6-107">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="d1ce6-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="d1ce6-108">Определяет интерфейс для вызываемого сервером автоматического вложения отладчика.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="d1ce6-109">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="d1ce6-110">Объявляет методы для регистрации и отмены регистрации источника уведомления соединения.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="d1ce6-111">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="d1ce6-112">Объявляет методы для уведомления приемника.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="d1ce6-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="d1ce6-114">Объявляет метод для установки фильтров оповещения.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="d1ce6-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="d1ce6-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="d1ce6-116">Предоставляет сведения для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="d1ce6-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="d1ce6-117">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="d1ce6-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="d1ce6-118">Этот интерфейс является дополнением к чтения [интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d1ce6-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="d1ce6-119">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="d1ce6-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="d1ce6-120">Разрешает определение сведений о методе необязательный асинхронный метод символ.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="d1ce6-121">Необходимо использовать открытый метод (то есть, между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="d1ce6-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="d1ce6-122">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="d1ce6-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="d1ce6-123">Представляет модуль привязки символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="d1ce6-124">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="d1ce6-125">Представляет модуль привязки символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="d1ce6-126">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="d1ce6-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="d1ce6-127">Представляет модуль привязки символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="d1ce6-128">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="d1ce6-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="d1ce6-129">Предоставляет доступ к неуправляемым константам.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="d1ce6-130">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="d1ce6-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="d1ce6-131">Освобождает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="d1ce6-132">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="d1ce6-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="d1ce6-133">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="d1ce6-134">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="d1ce6-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="d1ce6-135">Предоставляет методы для записи в документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="d1ce6-136">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="d1ce6-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="d1ce6-137">Предоставляет методы для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="d1ce6-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="d1ce6-138">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="d1ce6-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="d1ce6-139">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="d1ce6-140">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="d1ce6-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="d1ce6-141">Представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="d1ce6-142">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="d1ce6-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="d1ce6-143">Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="d1ce6-144">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="d1ce6-145">Получает метод средства чтения символов, получив токен метода и номеру версии редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="d1ce6-146">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="d1ce6-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="d1ce6-147">Предоставляет методы, получающие сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="d1ce6-148">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="d1ce6-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="d1ce6-149">Представляет лексическую область видимости в пределах одного метода.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="d1ce6-150">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="d1ce6-151">Представляет лексическую область в методе и расширяет `ISymUnmanagedScope` интерфейс с методами, которые получают сведения о константы, определенные в области...</span><span class="sxs-lookup"><span data-stu-id="d1ce6-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="d1ce6-152">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="d1ce6-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="d1ce6-153">Предоставляет данные сервера источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="d1ce6-154">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="d1ce6-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="d1ce6-155">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="d1ce6-156">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="d1ce6-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="d1ce6-157">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="d1ce6-158">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d1ce6-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="d1ce6-159">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="d1ce6-160">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="d1ce6-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="d1ce6-161">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="d1ce6-162">Расширяет `ISymUnmanagedWriter` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="d1ce6-163">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="d1ce6-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="d1ce6-164">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="d1ce6-165">Расширяет `ISymUnmanagedWriter` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="d1ce6-166">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="d1ce6-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="d1ce6-167">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="d1ce6-168">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="d1ce6-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="d1ce6-169">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="d1ce6-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1ce6-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d1ce6-170">Related Sections</span></span>  
 [<span data-ttu-id="d1ce6-171">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d1ce6-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="d1ce6-172">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d1ce6-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="d1ce6-173">Отладка</span><span class="sxs-lookup"><span data-stu-id="d1ce6-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
