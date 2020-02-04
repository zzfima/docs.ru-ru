---
title: 'Метод ICorDebugVariableHomeEnum:: Next'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 2bb6fee00bb99555bc19f35e1250880cc3985f7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790927"
---
# <a name="icordebugvariablehomeenumnext-method"></a>Метод ICorDebugVariableHomeEnum:: Next
Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество объектов, которые должны быть получены.  
  
 `homes`  
 Массив указателей, каждый из которых указывает на объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) , предоставляющий сведения о локальной переменной или аргументе функции.  
  
 `pceltFetched`  
 заполняет Число экземпляров, фактически возвращаемых в объектах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает следующие значения.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Метод завершился успешно.|  
|`S_FALSE`|Фактическое число полученных экземпляров, как отражается в `pceltFetched`, меньше, чем количество запрошенных экземпляров.|  
  
## <a name="remarks"></a>Заметки  
 Метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) извлекает не более `celt` объектов, начиная с текущей позиции перечислителя. Когда метод возвращает значение, `pceltFetched` содержит фактическое число извлеченных объектов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
