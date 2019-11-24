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
ms.openlocfilehash: 7ae978f5d2c9f7e90f4549c15a3935b441eabf04
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434011"
---
# <a name="isymunmanagedreader-interface"></a>Интерфейс ISymUnmanagedReader
Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Finds a document.|  
|[Метод GetDocuments](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Returns an array of all the documents defined in the symbol store.|  
|[Метод GetDocumentVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Gets the specified version of the specified document.|  
|[Метод GetGlobalVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Returns all global variables.|  
|[Метод GetMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Gets a symbol reader method, given a method token.|  
|[Метод GetMethodByVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Gets a symbol reader method, given a method token and an edit-and-copy version number.|  
|[Метод GetMethodFromDocumentPosition](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Returns the method that contains the breakpoint at the given position in a document.|  
|[Метод GetMethodsFromDocumentPosition](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Returns an array of methods, each of which contains the breakpoint at the given position in a document.|  
|[Метод GetMethodVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Gets the method version.|  
|[Метод GetNamespaces](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Gets the namespaces defined at global scope within this symbol store.|  
|[Метод GetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Gets a custom attribute based upon its name.|  
|[Метод GetSymbolStoreFileName](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Provides the on-disk file name of the symbol store.|  
|[Метод GetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Returns the method that was specified as the user entry point for the module, if any.|  
|[Метод GetVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Return a non-local variable, given its parent and name.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.|  
|[Метод ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Заменяет имеющееся хранилище символов разностным хранилищем символов.|  
|[Метод UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Обновляет существующее хранилище символов разностным хранилищем символов.|  
  
## <a name="requirements"></a>Требования  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
