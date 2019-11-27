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
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="2c80e-102">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2c80e-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="2c80e-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору создавать символьные сведения для использования отладчиком.</span><span class="sxs-lookup"><span data-stu-id="2c80e-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c80e-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2c80e-104">In This Section</span></span>  
 [<span data-ttu-id="2c80e-105">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="2c80e-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="2c80e-106">Предоставляет методы, отображающие текущие сведения о привязке для выполняющегося приложения.</span><span class="sxs-lookup"><span data-stu-id="2c80e-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="2c80e-107">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="2c80e-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="2c80e-108">Определяет интерфейс для автоматического присоединения отладчика, вызываемого сервером.</span><span class="sxs-lookup"><span data-stu-id="2c80e-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="2c80e-109">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="2c80e-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="2c80e-110">Объявляет методы для регистрации и отмены регистрации источника уведомления о соединении.</span><span class="sxs-lookup"><span data-stu-id="2c80e-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="2c80e-111">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="2c80e-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="2c80e-112">Объявляет методы для уведомления о приемнике.</span><span class="sxs-lookup"><span data-stu-id="2c80e-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="2c80e-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="2c80e-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="2c80e-114">Объявляет метод для установки фильтров уведомлений.</span><span class="sxs-lookup"><span data-stu-id="2c80e-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="2c80e-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="2c80e-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="2c80e-116">Предоставляет сведения для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="2c80e-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="2c80e-117">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="2c80e-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="2c80e-118">Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.</span><span class="sxs-lookup"><span data-stu-id="2c80e-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="2c80e-119">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="2c80e-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="2c80e-120">Разрешает определение дополнительных сведений о асинхронном методе для каждого символа метода.</span><span class="sxs-lookup"><span data-stu-id="2c80e-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="2c80e-121">Должен использовать с открытым методом (то есть между вызовами [метода опенмесод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)и [методом клосемесод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="2c80e-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="2c80e-122">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="2c80e-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="2c80e-123">Представляет связыватель символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2c80e-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="2c80e-124">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="2c80e-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="2c80e-125">Представляет связыватель символов для неуправляемого кода и расширяет интерфейс `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="2c80e-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="2c80e-126">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="2c80e-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="2c80e-127">Представляет связыватель символов для неуправляемого кода и расширяет интерфейс `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="2c80e-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="2c80e-128">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="2c80e-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="2c80e-129">Предоставляет доступ к неуправляемым константам.</span><span class="sxs-lookup"><span data-stu-id="2c80e-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="2c80e-130">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="2c80e-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="2c80e-131">Уничтожает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2c80e-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="2c80e-132">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="2c80e-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="2c80e-133">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2c80e-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="2c80e-134">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="2c80e-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="2c80e-135">Предоставляет методы для записи в документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2c80e-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="2c80e-136">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="2c80e-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="2c80e-137">Предоставляет методы для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="2c80e-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="2c80e-138">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="2c80e-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="2c80e-139">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2c80e-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="2c80e-140">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="2c80e-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="2c80e-141">Представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="2c80e-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="2c80e-142">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="2c80e-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="2c80e-143">Представляет средство чтения символов, предоставляющее доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2c80e-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="2c80e-144">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="2c80e-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="2c80e-145">Возвращает метод чтения символов по заданному токену метода и номеру версии для редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="2c80e-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="2c80e-146">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="2c80e-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="2c80e-147">Предоставляет методы, которые получают сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="2c80e-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="2c80e-148">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="2c80e-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="2c80e-149">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="2c80e-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="2c80e-150">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="2c80e-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="2c80e-151">Представляет лексическую область внутри метода и расширяет интерфейс `ISymUnmanagedScope` с помощью методов, которые получают сведения о константах, определенных в области.</span><span class="sxs-lookup"><span data-stu-id="2c80e-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="2c80e-152">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="2c80e-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="2c80e-153">Предоставляет данные сервера-источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="2c80e-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="2c80e-154">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="2c80e-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="2c80e-155">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="2c80e-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="2c80e-156">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="2c80e-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="2c80e-157">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="2c80e-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="2c80e-158">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="2c80e-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="2c80e-159">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="2c80e-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="2c80e-160">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="2c80e-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="2c80e-161">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="2c80e-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="2c80e-162">Расширяет интерфейс `ISymUnmanagedWriter`.</span><span class="sxs-lookup"><span data-stu-id="2c80e-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="2c80e-163">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="2c80e-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="2c80e-164">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="2c80e-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="2c80e-165">Расширяет интерфейс `ISymUnmanagedWriter`.</span><span class="sxs-lookup"><span data-stu-id="2c80e-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="2c80e-166">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="2c80e-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="2c80e-167">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="2c80e-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="2c80e-168">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="2c80e-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="2c80e-169">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="2c80e-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2c80e-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2c80e-170">Related Sections</span></span>  
 [<span data-ttu-id="2c80e-171">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2c80e-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="2c80e-172">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2c80e-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="2c80e-173">Отладка</span><span class="sxs-lookup"><span data-stu-id="2c80e-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
