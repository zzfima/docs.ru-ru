---
title: "Интерфейс ISymUnmanagedReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="8cff5-102">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="8cff5-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="8cff5-103">Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8cff5-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cff5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8cff5-104">Methods</span></span>  
  
|<span data-ttu-id="8cff5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8cff5-105">Method</span></span>|<span data-ttu-id="8cff5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8cff5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cff5-107">Метод GetDocument</span><span class="sxs-lookup"><span data-stu-id="8cff5-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="8cff5-108">Обнаружен документ.</span><span class="sxs-lookup"><span data-stu-id="8cff5-108">Finds a document.</span></span>|  
|[<span data-ttu-id="8cff5-109">Метод GetDocuments</span><span class="sxs-lookup"><span data-stu-id="8cff5-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="8cff5-110">Возвращает массив всех документов, определенных в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8cff5-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="8cff5-111">Метод GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="8cff5-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="8cff5-112">Получает указанную версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="8cff5-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="8cff5-113">Метод GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="8cff5-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="8cff5-114">Возвращает все глобальные переменные.</span><span class="sxs-lookup"><span data-stu-id="8cff5-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="8cff5-115">Метод GetMethod</span><span class="sxs-lookup"><span data-stu-id="8cff5-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="8cff5-116">Возвращает метод средства чтения символов, маркер метода.</span><span class="sxs-lookup"><span data-stu-id="8cff5-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="8cff5-117">Метод GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="8cff5-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="8cff5-118">Получает метод средства чтения символов, заданному маркеру метода и номеру версии редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="8cff5-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="8cff5-119">Метод GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="8cff5-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="8cff5-120">Возвращает метод, который содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="8cff5-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="8cff5-121">Метод GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="8cff5-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="8cff5-122">Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="8cff5-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="8cff5-123">Метод GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="8cff5-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="8cff5-124">Получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="8cff5-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="8cff5-125">Getnamespaces-метод</span><span class="sxs-lookup"><span data-stu-id="8cff5-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="8cff5-126">Возвращает пространства имен, определенные в глобальной области в данном хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8cff5-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="8cff5-127">Метод GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="8cff5-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="8cff5-128">Получает пользовательский атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="8cff5-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="8cff5-129">Метод GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="8cff5-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="8cff5-130">Задает имя файла на диске в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8cff5-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="8cff5-131">Метод GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="8cff5-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="8cff5-132">Возвращает метод, заданный в качестве точки входа пользователя для модуля, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="8cff5-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="8cff5-133">Метод GetVariables</span><span class="sxs-lookup"><span data-stu-id="8cff5-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="8cff5-134">Возвращать внешней переменной, ее родительскому объекту и имя.</span><span class="sxs-lookup"><span data-stu-id="8cff5-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="8cff5-135">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="8cff5-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="8cff5-136">Инициализирует средства чтения символов, при этом интерфейс импорта метаданных, данное средство чтения связанного с, а также имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="8cff5-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="8cff5-137">Метод ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="8cff5-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="8cff5-138">Заменяет имеющееся хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="8cff5-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="8cff5-139">Метод UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="8cff5-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="8cff5-140">Обновляет существующее хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="8cff5-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8cff5-141">Требования</span><span class="sxs-lookup"><span data-stu-id="8cff5-141">Requirements</span></span>  
 <span data-ttu-id="8cff5-142">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8cff5-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cff5-143">См. также</span><span class="sxs-lookup"><span data-stu-id="8cff5-143">See Also</span></span>  
 [<span data-ttu-id="8cff5-144">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="8cff5-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="8cff5-145">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="8cff5-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
