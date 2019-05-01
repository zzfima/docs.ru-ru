---
title: Интерфейс ISymUnmanagedReader
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0782533f773b69eeeb0b89175e5b22c61e822ed9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986366"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="d9317-102">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="d9317-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="d9317-103">Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d9317-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9317-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d9317-104">Methods</span></span>  
  
|<span data-ttu-id="d9317-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d9317-105">Method</span></span>|<span data-ttu-id="d9317-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d9317-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9317-107">Метод GetDocument</span><span class="sxs-lookup"><span data-stu-id="d9317-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="d9317-108">Находит документ.</span><span class="sxs-lookup"><span data-stu-id="d9317-108">Finds a document.</span></span>|  
|[<span data-ttu-id="d9317-109">Метод GetDocuments</span><span class="sxs-lookup"><span data-stu-id="d9317-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="d9317-110">Возвращает массив всех документов, определенных в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d9317-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="d9317-111">Метод GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="d9317-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="d9317-112">Получает указанную версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="d9317-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="d9317-113">Метод GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="d9317-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="d9317-114">Возвращает все глобальные переменные.</span><span class="sxs-lookup"><span data-stu-id="d9317-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="d9317-115">Метод GetMethod</span><span class="sxs-lookup"><span data-stu-id="d9317-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="d9317-116">Возвращает метода средства чтения символов, маркер метода.</span><span class="sxs-lookup"><span data-stu-id="d9317-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="d9317-117">Метод GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="d9317-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="d9317-118">Получает метода средства чтения символов, получив токен метода и номеру версии редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="d9317-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="d9317-119">Метод GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="d9317-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="d9317-120">Возвращает метод, который содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="d9317-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="d9317-121">Метод GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="d9317-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="d9317-122">Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="d9317-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="d9317-123">Метод GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="d9317-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="d9317-124">Получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="d9317-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="d9317-125">Метод GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="d9317-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="d9317-126">Получает пространства имен, определенные в глобальной области в данном хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d9317-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="d9317-127">Метод GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="d9317-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="d9317-128">Получает настраиваемый атрибут, в зависимости от его имени.</span><span class="sxs-lookup"><span data-stu-id="d9317-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="d9317-129">Метод GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="d9317-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="d9317-130">Предоставляет имя файла на диске в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d9317-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="d9317-131">Метод GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="d9317-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="d9317-132">Возвращает метод, который был указан в качестве точки входа пользователя для модуля, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="d9317-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="d9317-133">Метод GetVariables</span><span class="sxs-lookup"><span data-stu-id="d9317-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="d9317-134">Возврат не являющейся локальной переменной, ее родительскому объекту и имя.</span><span class="sxs-lookup"><span data-stu-id="d9317-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="d9317-135">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="d9317-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="d9317-136">Инициализирует средство чтения символов с интерфейсом средства импорта метаданных, что средство чтения будет сопоставлено, а также имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="d9317-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="d9317-137">Метод ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="d9317-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="d9317-138">Заменяет имеющееся хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="d9317-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="d9317-139">Метод UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="d9317-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="d9317-140">Обновляет существующее хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="d9317-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9317-141">Требования</span><span class="sxs-lookup"><span data-stu-id="d9317-141">Requirements</span></span>  
 <span data-ttu-id="d9317-142">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9317-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9317-143">См. также</span><span class="sxs-lookup"><span data-stu-id="d9317-143">See also</span></span>

- [<span data-ttu-id="d9317-144">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d9317-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d9317-145">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="d9317-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
