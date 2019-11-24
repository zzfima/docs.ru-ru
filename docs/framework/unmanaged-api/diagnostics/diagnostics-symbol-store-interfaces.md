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
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="5c788-102">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5c788-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="5c788-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span><span class="sxs-lookup"><span data-stu-id="5c788-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c788-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="5c788-104">In This Section</span></span>  
 [<span data-ttu-id="5c788-105">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="5c788-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="5c788-106">Provides methods that display current binding information about the running application.</span><span class="sxs-lookup"><span data-stu-id="5c788-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="5c788-107">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="5c788-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="5c788-108">Defines the interface for a server-invoked debugger auto attach.</span><span class="sxs-lookup"><span data-stu-id="5c788-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="5c788-109">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="5c788-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="5c788-110">Declares methods for registering and unregistering a connection notification source.</span><span class="sxs-lookup"><span data-stu-id="5c788-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="5c788-111">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="5c788-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="5c788-112">Declares methods for sink notification.</span><span class="sxs-lookup"><span data-stu-id="5c788-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="5c788-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="5c788-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="5c788-114">Declares a method for setting notification filters.</span><span class="sxs-lookup"><span data-stu-id="5c788-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="5c788-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="5c788-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="5c788-116">Provides information for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="5c788-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="5c788-117">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="5c788-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="5c788-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c788-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="5c788-119">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="5c788-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="5c788-120">Allows definition of optional async method information per method symbol.</span><span class="sxs-lookup"><span data-stu-id="5c788-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="5c788-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="5c788-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="5c788-122">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="5c788-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="5c788-123">Represents a symbol binder for unmanaged code.</span><span class="sxs-lookup"><span data-stu-id="5c788-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="5c788-124">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="5c788-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="5c788-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="5c788-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="5c788-126">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="5c788-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="5c788-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="5c788-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="5c788-128">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="5c788-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="5c788-129">Provides access to unmanaged constants.</span><span class="sxs-lookup"><span data-stu-id="5c788-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="5c788-130">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="5c788-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="5c788-131">Disposes of unmanaged resources.</span><span class="sxs-lookup"><span data-stu-id="5c788-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="5c788-132">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="5c788-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="5c788-133">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="5c788-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="5c788-134">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="5c788-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="5c788-135">Предоставляет методы для записи в документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="5c788-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="5c788-136">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="5c788-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="5c788-137">Provides methods for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="5c788-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="5c788-138">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="5c788-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="5c788-139">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="5c788-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="5c788-140">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="5c788-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="5c788-141">Represents a namespace.</span><span class="sxs-lookup"><span data-stu-id="5c788-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="5c788-142">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="5c788-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="5c788-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span><span class="sxs-lookup"><span data-stu-id="5c788-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="5c788-144">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="5c788-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="5c788-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span><span class="sxs-lookup"><span data-stu-id="5c788-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="5c788-146">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5c788-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="5c788-147">Provides methods that get symbol search information.</span><span class="sxs-lookup"><span data-stu-id="5c788-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="5c788-148">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="5c788-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="5c788-149">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="5c788-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="5c788-150">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="5c788-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="5c788-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span><span class="sxs-lookup"><span data-stu-id="5c788-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="5c788-152">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="5c788-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="5c788-153">Provides source server data for a module.</span><span class="sxs-lookup"><span data-stu-id="5c788-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="5c788-154">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5c788-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="5c788-155">Provides methods that get information about the search path.</span><span class="sxs-lookup"><span data-stu-id="5c788-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="5c788-156">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="5c788-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="5c788-157">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="5c788-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="5c788-158">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="5c788-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="5c788-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="5c788-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="5c788-160">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="5c788-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="5c788-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="5c788-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="5c788-162">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="5c788-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="5c788-163">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="5c788-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="5c788-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="5c788-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="5c788-165">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="5c788-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="5c788-166">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="5c788-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="5c788-167">ISymUnmanagedWriter4 interface.</span><span class="sxs-lookup"><span data-stu-id="5c788-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="5c788-168">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="5c788-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="5c788-169">ISymUnmanagedWriter5 interface.</span><span class="sxs-lookup"><span data-stu-id="5c788-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c788-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5c788-170">Related Sections</span></span>  
 [<span data-ttu-id="5c788-171">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5c788-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="5c788-172">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5c788-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="5c788-173">Отладка</span><span class="sxs-lookup"><span data-stu-id="5c788-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
