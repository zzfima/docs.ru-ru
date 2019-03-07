---
title: Метод ICorDebugILFrame3::GetReturnValueForILOffset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a01e2fcc7dc00d3a57272abb04ebcecc6d5f74a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467087"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>Метод ICorDebugILFrame3::GetReturnValueForILOffset
Возвращает объект «ICorDebugValue», который инкапсулирует возвращаемое значение функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ILOffset`  
 Смещение на промежуточном Языке. См. раздел примeчаний.  
  
 `ppReturnValue`  
 Указатель на адрес объекта интерфейса «ICorDebugValue», предоставляющий сведения о возвращаемом значении вызова функции.  
  
## <a name="remarks"></a>Примечания  
 Этот метод используется вместе с [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) способ получения возвращаемого значения метода. Это особенно полезно при использовании методов, учитываются, возвращаемые значения, как показано в следующих двух примерах кода. В первом примере вызывается <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метод, но игнорирует возвращаемое значение метода.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Во втором примере показано гораздо более общие проблемы при отладке. Поскольку метод используется в качестве аргумента в вызове метода, его возвращаемое значение доступно только в том случае, когда отладчик проходит через вызываемый метод. Во многих случаях особенно в том случае, если вызываемый метод определен во внешней библиотеке, которая не поддерживается.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Если передать [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод смещения на сайт вызова функции промежуточном языке, он возвращает один или несколько смещений в машинном коде. Отладчик может установить точки останова на этих естественных смещениях функции. Когда отладчик достигает одной из точек останова, затем можно передать то же смещение IL, которое было передано в этот метод для получения возвращаемого значения. Затем он должен очистить все точки останова, он задан.  
  
> [!WARNING]
>  [Метод ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) и `ICorDebugILFrame3::GetReturnValueForILOffset` методы позволяют получить сведения о возвращаемом значении только для ссылочных типов. Получение сведений о возвращаемое значение из типов значений (то есть всех типов, производных от <xref:System.ValueType>) не поддерживается.  
  
 Смещение на промежуточном Языке, определяемое `ILOffset` должно находиться на сайт вызова функции, а отлаживаемый объект должен быть остановлен на точку останова в исходное смещение, возвращенный [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод для то же смещение IL. Если отлаживаемый объект не останавливается на правильное расположение для заданного смещения IL, API завершится ошибкой.  
  
 Если вызов функции не возвращает значение, API завершится ошибкой.  
  
 `ICorDebugILFrame3::GetReturnValueForILOffset` Метод доступен только на x86 и системах AMD64.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [Интерфейс ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
