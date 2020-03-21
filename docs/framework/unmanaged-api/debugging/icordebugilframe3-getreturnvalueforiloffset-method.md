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
ms.openlocfilehash: 0d1ef6c1369fd399f5b36b24a21c4b5d7f1e80fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178818"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>Метод ICorDebugILFrame3::GetReturnValueForILOffset
Получает объект ICorDebugValue, который инкапсулирует значение возврата функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ILOffset`  
 IL смещения. См. раздел «Примечания».  
  
 `ppReturnValue`  
 Указатель на адрес объекта интерфейса "ICorDebugValue", который предоставляет информацию о значении возврата вызова функции.  
  
## <a name="remarks"></a>Remarks  
 Этот метод используется вместе с [методом ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) для получения значения возврата метода. Это особенно полезно в случае методов, значения возврата которых игнорируются, как в следующих двух примерах кода. Первый пример <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> вызывает метод, но игнорирует значение возврата метода.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Второй пример иллюстрирует гораздо более распространенную проблему при отладке. Поскольку метод используется в качестве аргумента в вызове метода, его значение возврата доступно только тогда, когда отладчик проходит через вызванный метод. Во многих случаях, особенно когда вызовный метод определяется во внешней библиотеке, это невозможно.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Если вы проходите [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) метод IL смещения на сайт вызова функции, он возвращает один или несколько родных смещений. Затем отладчик может устанавливать точки разрыва на этих родных смещениях в функции. Когда отладчик попадает в одну из точек разрыва, вы можете передать тот же il смещения, что вы прошли к этому методу, чтобы получить значение возврата. Затем отладчик должен очистить все установленные моменты разрыва.  
  
> [!WARNING]
> [ICorDebugCode3::GetReturnValueLiveOffset метод](icordebugcode3-getreturnvalueliveoffset-method.md) `ICorDebugILFrame3::GetReturnValueForILOffset` и методы позволяют получить информацию о значении возврата только для эталонных типов. Извлечение информации о значении возврата из типов <xref:System.ValueType>значений (т.е. все типы, которые вытекают из ) не поддерживается.  
  
 Смещение IL, `ILOffset` указанное параметром, должно находиться на сайте вызова функции, а отладка должна быть остановлена в точке разрыва, установленной на родном смещении, возвращенном [Методом ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) для того же смещения IL. Если отладка не остановлена в нужном месте для указанного смещения IL, API выйдет из строя.  
  
 Если вызов функции не возвращает значение, API выйдет из строя.  
  
 Метод `ICorDebugILFrame3::GetReturnValueForILOffset` доступен только на системах x86 и AMD64.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)
- [Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)
