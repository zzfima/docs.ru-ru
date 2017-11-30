---
title: "Метод ICorDebugILFrame3::GetReturnValueForILOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- csharp
- vb
api_name: ICorDebugILFrame3.GetReturnValueForILOffset
api_location: mscordbi.dll
api_type: COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6e51043fe3824154f1333969134209a685f98914
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>Метод ICorDebugILFrame3::GetReturnValueForILOffset
Возвращает объект «ICorDebugValue», инкапсулирующий возвращаемое значение функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ILOffset`  
 Смещение на промежуточном Языке. См. раздел примeчаний.  
  
 `ppReturnValue`  
 Указатель на адрес объекта интерфейса «ICorDebugValue» с информацией о возвращаемое значение вызова функции.  
  
## <a name="remarks"></a>Примечания  
 Этот метод используется вместе с [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод для получения возвращаемого значения метода. Это особенно полезно в случае методы, возвращаемые значения учитываются, как показано в следующих двух примерах кода. В первом примере вызывается <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метода, но игнорирует возвращаемое значение метода.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Во втором примере показан гораздо более распространенной проблемой для отладки. Поскольку метод используется в качестве аргумента в вызове метода, возвращаемого значения доступно только в том случае, если отладчик пошаговое выполнение вызываемого метода. Во многих случаях особенно в том случае, если вызываемый метод определен во внешней библиотеке, это невозможно.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Если передать [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод в IL смещение к место вызова функции возвращает один или несколько собственные смещения. Затем отладчик можно установить точки останова на этих смещениях машинного кода в функцию. Если отладчик обнаруживает одной из точек останова, затем можно передать одинаковое смещение IL, который передан в этот метод для получения возвращаемого значения. Отладчик должен выполнить очистку все точки останова, которые оно задано.  
  
> [!WARNING]
>  [Метод ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) и `ICorDebugILFrame3::GetReturnValueForILOffset` методы позволяют получить сведения о возвращаемых значениях только для ссылочных типов. Получение сведений о возвращаемое значение от типов значений (то есть, все типы, производные от <xref:System.ValueType>) не поддерживается.  
  
 Смещение на промежуточном Языке, определяемое `ILOffset` параметр должен быть в месте вызова функции и отлаживаемого кода должна быть остановлена в точку останова в исходное смещение, возвращенных [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод для того же смещение на промежуточном Языке. Если отлаживаемый процесс не остановлен в правильном расположении для указанного смещение на промежуточном Языке, произойдет сбой API.  
  
 Если вызов функции не возвращает значение, произойдет сбой API.  
  
 `ICorDebugILFrame3::GetReturnValueForILOffset` Метод доступен только для x86 86 и AMD64 систем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [Интерфейс ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
