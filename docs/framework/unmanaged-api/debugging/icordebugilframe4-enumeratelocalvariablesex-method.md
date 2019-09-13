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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3deb497c3e842e25bcaa46a867dd61ea4a1c3804
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926819"
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
 окне Элемент перечисления [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) , указывающий, включены ли в кадр переменные, добавленные в инструментирование ReJIT профилировщика.  
  
 `ppValueEnum`  
 заполняет Указатель на адрес объекта "ICorDebugValueEnum", который является перечислителем для локальных переменных в этом кадре.  
  
## <a name="remarks"></a>Примечания  
 Этот метод аналогичен методу [енумерателокалвариаблес](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) , за исключением того, что он дополнительно получает доступ к переменным, добавленным в инструментарий профилировщика ReJIT. Параметр `flags` в`ILCODE_ORIGINAL_IL` эквивалентен вызову [ICorDebugILFrame:: енумерателокалвариаблес](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md). Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.  
  
 Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT Руководство](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
