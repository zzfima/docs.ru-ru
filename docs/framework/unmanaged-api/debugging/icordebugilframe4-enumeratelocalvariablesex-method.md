---
title: Метод ICorDebugILFrame4::EnumerateLocalVariablesEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: afeec3df03fc2b122ca8deb8123b79314b5e3837
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782418"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a>Метод ICorDebugILFrame4::EnumerateLocalVariablesEx
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает перечислитель для локальной переменной в кадре и может включать переменные, добавленные в инструментарий ReJIT профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `flags`  
 окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включены ли в кадр переменные, добавленные в инструментирование ReJIT профилировщика.  
  
 `ppValueEnum`  
 заполняет Указатель на адрес объекта "ICorDebugValueEnum", который является перечислителем для локальных переменных в этом кадре.  
  
## <a name="remarks"></a>Заметки  
 Этот метод аналогичен методу [енумерателокалвариаблес](icordebugilframe-enumeratelocalvariables-method.md) , за исключением того, что он дополнительно получает доступ к переменным, добавленным в инструментарий профилировщика ReJIT. Установка `flags` в `ILCODE_ORIGINAL_IL` эквивалентно вызову [ICorDebugILFrame:: енумерателокалвариаблес](icordebugilframe-enumeratelocalvariables-method.md). Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.  
  
 Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [ReJIT: руководство](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
