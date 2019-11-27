---
title: Интерфейс ISymUnmanagedDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449103"
---
# <a name="isymunmanageddocument-interface"></a>Интерфейс ISymUnmanagedDocument
Представляет документ, на который ссылается хранилище символов. Документ определяется по универсальному указателю ресурсов (URL-адрес) и GUID типа документа. Документ можно разместить независимо от того, как он хранится, используя URL-адрес и GUID типа документа. Вы можете сохранить источник документа в хранилище символов и получить его через этот интерфейс.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод FindClosestLine](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|Возвращает ближайшую строку, которая является точкой последовательности, с учетом строки в этом документе, которая может быть или не являться точкой последовательности.|  
|[Метод GetCheckSum](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|Возвращает контрольную сумму.|  
|[Метод GetCheckSumAlgorithmId](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|Возвращает идентификатор алгоритма контрольной суммы или возвращает идентификатор GUID всех нулей, если контрольная сумма отсутствует.|  
|[Метод GetDocumentType](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|Возвращает тип документа этого документа.|  
|[Метод GetLanguage](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|Возвращает идентификатор языка этого документа.|  
|[Метод GetLanguageVendor](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|Получает поставщика языка этого документа.|  
|[Метод GetSourceLength](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|Возвращает длину внедренного источника в байтах.|  
|[Метод GetSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|Возвращает указанный диапазон внедренного источника в заданный буфер.|  
|[Метод GetURL](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|Возвращает URL-адрес для этого документа.|  
|[Метод HasEmbeddedSource](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|Возвращает `true`, если документ содержит исходный код, внедренный в отладочные символы; в противном случае возвращает `false`.|  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
