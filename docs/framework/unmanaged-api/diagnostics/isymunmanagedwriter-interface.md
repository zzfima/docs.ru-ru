---
title: Интерфейс ISymUnmanagedWriter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
ms.openlocfilehash: fc19ee25e903046daef376e4297c8feb3d01ad47
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427934"
---
# <a name="isymunmanagedwriter-interface"></a>Интерфейс ISymUnmanagedWriter
Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Закрывает модуль записи символов без фиксации символов в хранилище символов.|  
|[Метод Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Закрывает модуль записи символов после фиксации символов в хранилище символов.|  
|[Метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Закрывает текущий метод. После закрытия метода в нем нельзя определять символы.|  
|[Метод CloseNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Закрывает Последнее открытое пространство имен.|  
|[Метод CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Закрывает текущую лексическую область видимости.|  
|[Метод DefineConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Определяет имя для постоянного значения.|  
|[Метод DefineDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Определяет исходный документ.|  
|[Метод DefineField](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Определяет одну переменную, не находящиеся в методе.|  
|[Метод DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Определяет одну глобальную переменную.|  
|[Метод DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Определяет одну переменную в текущей лексической области видимости.|  
|[Метод DefineParameter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Определяет один параметр в текущем методе.|  
|[Метод DefineSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Определяет группу точек следования в текущем методе.|  
|[Метод GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Возвращает сведения, необходимые компилятору для записи записи каталога отладки в заголовке переносимого исполняемого файла (PE).|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, и задает имя выходного файла, в который будут записываться отладочные символы.|  
|[Метод Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, задает имя выходного файла, в который будут записываться символы отладки, и задает конечное расположение файла базы данных программы (PDB).|  
|[Метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Открывает метод, в который порождается символьная информация.|  
|[Метод OpenNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Открывает новое пространство имен.|  
|[Метод OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Открывает новую лексическую область видимости в текущем методе.|  
|[Метод RemapToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Уведомляет средство записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.|  
|[Метод SetMethodSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Задает истинное начало и конец метода в исходном файле.|  
|[Метод SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Определяет диапазон смещений для заданной лексической области видимости.|  
|[Метод SetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Определяет настраиваемый атрибут на основе его имени.|  
|[Метод SetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Задает определяемый пользователем метод, являющийся точкой входа для этого модуля.|  
|[Метод UsingNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Указывает, что данное полное имя пространства имен используется в открытой лексической области.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [Интерфейс ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
