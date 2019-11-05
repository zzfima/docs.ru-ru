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
ms.openlocfilehash: c7419e5c3677b5679a0ca5c234463ae6e205b7d1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090365"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>Метод ICorDebugILFrame3::GetReturnValueForILOffset
Возвращает объект ICorDebugValue, инкапсулирующий возвращаемое значение функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ILOffset`  
 Смещение IL. См. раздел примeчаний.  
  
 `ppReturnValue`  
 Указатель на адрес объекта "ICorDebugValue" интерфейса, который предоставляет сведения о возвращаемом значении вызова функции.  
  
## <a name="remarks"></a>Заметки  
 Этот метод используется вместе с методом [ICorDebugCode3:: жетретурнвалуеливеоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) для получения возвращаемого значения метода. Это особенно полезно в случае с методами, возвращаемые значения которых игнорируются, как в следующих двух примерах кода. Первый пример вызывает метод <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>, но игнорирует возвращаемое значение метода.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Во втором примере показана гораздо более распространенная проблема при отладке. Так как метод используется в качестве аргумента в вызове метода, его возвращаемое значение доступно только в том случае, если отладчик проходит через вызываемый метод. Во многих случаях, особенно если вызванный метод определен во внешней библиотеке, это невозможно.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Если передать метод [ICorDebugCode3:: жетретурнвалуеливеоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) в качестве смещения Il на сайт вызова функции, он возвращает одно или несколько машинных смещений. Затем отладчик может установить точки останова для этих собственных смещений в функции. Когда отладчик обращается к одной из точек останова, можно передать то же смещение IL, которое вы передали этому методу для получения возвращаемого значения. Затем отладчик должен очистить все заданные точки останова.  
  
> [!WARNING]
> Методы [ICorDebugCode3:: жетретурнвалуеливеоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) и `ICorDebugILFrame3::GetReturnValueForILOffset` позволяют получать сведения о возвращаемых значениях только для ссылочных типов. Получение сведений о возвращаемом значении из типов значений (то есть все типы, производные от <xref:System.ValueType>) не поддерживаются.  
  
 Смещение IL, заданное параметром `ILOffset`, должно находиться на сайте вызова функции, а отладка должна быть остановлена в точке останова, установленной в машинном смещении, возвращенном методом [ICorDebugCode3:: жетретурнвалуеливеоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) для того же смещения IL. Если отлаживаемая программа не остановлена в правильном расположении для указанного смещения IL, API завершится ошибкой.  
  
 Если вызов функции не возвращает значение, API завершится ошибкой.  
  
 Метод `ICorDebugILFrame3::GetReturnValueForILOffset` доступен только в системах на базе x86 и AMD64.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [Интерфейс ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
