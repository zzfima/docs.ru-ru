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
ms.openlocfilehash: a78616ea1dccdf82c4e00d23d2ff630c98cb4e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedreader-interface"></a>Интерфейс ISymUnmanagedReader
Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Обнаружен документ.|  
|[Метод GetDocuments](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Возвращает массив всех документов, определенных в хранилище символов.|  
|[Метод GetDocumentVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Получает указанную версию указанного документа.|  
|[Метод GetGlobalVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Возвращает все глобальные переменные.|  
|[Метод GetMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Возвращает метод средства чтения символов, маркер метода.|  
|[Метод GetMethodByVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Получает метод средства чтения символов, заданному маркеру метода и номеру версии редактирования и копирования.|  
|[Метод GetMethodFromDocumentPosition](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Возвращает метод, который содержит точку останова в заданной позиции в документе.|  
|[Метод GetMethodsFromDocumentPosition](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.|  
|[Метод GetMethodVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Получает версию метода.|  
|[Метод GetNamespaces](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Возвращает пространства имен, определенные в глобальной области в данном хранилище символов.|  
|[Метод GetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Получает пользовательский атрибут на основе его имени.|  
|[Метод GetSymbolStoreFileName](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Задает имя файла на диске в хранилище символов.|  
|[Метод GetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Возвращает метод, заданный в качестве точки входа пользователя для модуля, если таковые имеются.|  
|[Метод GetVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Возвращать внешней переменной, ее родительскому объекту и имя.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Инициализирует средства чтения символов, при этом интерфейс импорта метаданных, данное средство чтения связанного с, а также имя файла модуля.|  
|[Метод ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Заменяет имеющееся хранилище символов разностным хранилищем символов.|  
|[Метод UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Обновляет существующее хранилище символов разностным хранилищем символов.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
