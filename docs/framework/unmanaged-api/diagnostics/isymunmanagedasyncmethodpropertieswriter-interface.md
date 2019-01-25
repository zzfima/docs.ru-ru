---
title: Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d83270d0e7f5dabff8402f5f81dae20d4457d147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604262"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter
Можно задать сведения о методе необязательно async для каждого символа метод. Всегда используйте с помощью открытого метода; то есть между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Методы  
 Этот интерфейс содержит следующие методы:  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Определить группу async await операций в текущем методе.<br /><br /> Смещение каждого yield соответствует инструкции return оператором await, определение потенциальных yield. Каждый `breakpointMethod` / `breakpointOffset` пары определяет, где будет возобновлена асинхронную операцию; он может находиться в другой метод.|  
|[Метод DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Задает смещение для обработчика catch, созданный компилятором, который создает оболочку для асинхронного метода на промежуточном Языке.<br /><br /> Смещение на промежуточном Языке создаваемый catch используется отладчиком для обработки catch, как если бы это был не написанный пользователем код, несмотря на то, что эта проблема может возникнуть в коде пользовательского метода. В частности, он используется в ответ на **CatchHandlerFound** события исключения.|  
|[Метод DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Задает начальный метод, который инициирует асинхронную операцию.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
