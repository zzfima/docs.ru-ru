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
ms.openlocfilehash: 341a86f4c1c8367f979e193a6284bf89f1b03ca0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178805"
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
 (в) Член [пересчета ILCodeKind,](ilcodekind-enumeration.md) который определяет, включены ли в кадр переменные, добавленные в инструменты профайлера ReJIT.  
  
 `ppValueEnum`  
 (ваут) Указатель на адрес объекта "ICorDebugValueEnum", который является регистратором локальных переменных в этом кадре.  
  
## <a name="remarks"></a>Remarks  
 Этот метод аналогичен методу [EnumerateLocalVariables,](icordebugilframe-enumeratelocalvariables-method.md) за исключением того, что он дополнительно получает доступ к переменным, добавленным в инструментарий ReJIT. Установка `flags` `ILCODE_ORIGINAL_IL` эквивалентна вызову [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md). Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.  
  
 Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [ReJIT: Как-к руководству](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
