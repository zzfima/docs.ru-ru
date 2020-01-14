---
title: Метод ICorDebugILFrame4::GetLocalVariableEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: 89a8aa1f789ad71b04bc5fed8885f55ee25c4609
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937660"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>Метод ICorDebugILFrame4::GetLocalVariableEx
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает значение указанной локальной переменной в этом кадре стека промежуточного языка (IL) и дополнительно получает доступ к переменной, добавленной в инструментарий ReJIT профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `flags`  
 окне Элемент перечисления [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) , указывающий, включается ли переменная, добавленная в инструментирование профилировщика ReJIT, в кадр.  
  
 `dwIndex`  
 [в] Индекс локальной переменной в кадре стека промежуточного языка.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта ICorDebugValue, который представляет извлеченное значение.  
  
## <a name="remarks"></a>Заметки  
 Этот метод аналогичен методу [жетлокалвариабле](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) , за исключением того, что он дополнительно получает доступ к переменной, добавленной в инструментарий профилировщика ReJIT. Вызов этого метода с `flags` значением `ILCODE_ORIGINAL_IL` эквивалентно вызову [жетлокалвариабле](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); Если метод оснащен дополнительными локальными переменными, доступ к этим переменным невозможен. `ILCODE_REJIT_IL` обеспечивает отладчику доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, метод возвращает значение `E_INVALIDARG`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: руководство](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
