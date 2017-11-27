---
title: "Интерфейс ISymUnmanagedWriter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter
helpviewer_keywords: ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e74e625c911f35bdb7c20451b1babd02cdb7658
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter-interface"></a>Интерфейс ISymUnmanagedWriter
Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Abort-метод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Закрывает средство записи символов без передачи символов в хранилище символов.|  
|[Close-метод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Закрывает средство записи символов после передачи символов в хранилище символов.|  
|[Метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Закрывает текущий метод. После закрытия метода отсутствуют дополнительные символы могут определяться внутри него.|  
|[Метод CloseNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Закрывает последнее открыть пространство имен.|  
|[Метод CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Закрывает текущую лексическую область видимости.|  
|[Метод DefineConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Определяет имя для постоянного значения.|  
|[Метод DefineDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Определяет исходный документ.|  
|[Метод DefineField](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Определяет одну переменную вне метода.|  
|[Метод DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Определяет одну глобальную переменную.|  
|[Метод DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Определяет одну переменную в текущей лексической области видимости.|  
|[Метод DefineParameter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Определяет отдельный параметр в текущем методе.|  
|[Метод DefineSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Определяет группу точек следования в текущем методе.|  
|[Метод GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Возвращает информацию, необходимую для компилятора записать запись каталога отладки в заголовок переносимого исполняемого (PE) файла.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Задает интерфейс включения метаданных, с которым будет связано данное средство записи и задает имя выходного файла, в который записываются символы отладки.|  
|[Метод Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Задает интерфейс включения метаданных, с которым будет связано данное средство записи, задает имя выходного файла, в которую будут записаны символы отладки и задает конечное расположение файла базы данных (PDB) программы.|  
|[Метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Открывает метод в символ, который создается информация.|  
|[Метод OpenNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Открывает новое пространство имен.|  
|[Метод OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Открывает новую лексическую область видимости в текущем методе.|  
|[Метод RemapToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Уведомляет модуля записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.|  
|[Метод SetMethodSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Указывает истинные начало и конец метода в исходном файле.|  
|[Метод SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Определяет диапазон смещений для заданной лексической области видимости.|  
|[Метод SetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Определяет настраиваемый атрибут на основе его имени.|  
|[Метод SetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Задает пользовательский метод, являющегося точкой входа для этого модуля.|  
|[Метод UsingNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Указывает, что данный полным именем пространства имен используется в текущей открытой лексической области.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [Isymunmanagedwriter3-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
