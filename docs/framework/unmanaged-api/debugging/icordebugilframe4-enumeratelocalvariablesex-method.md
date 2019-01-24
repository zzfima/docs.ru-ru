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
ms.openlocfilehash: f770182ef8489d503ed092bb4c6cf43ae5b9ce10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663353"
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
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 [in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) член перечисления, указывающее, включаются ли в кадр переменным, добавленным в инструментарий ReJIT профилировщика.  
  
 `ppValueEnum`  
 [out] Указатель на адрес объекта «ICorDebugValueEnum», который является перечислителем для локальных переменных в кадре.  
  
## <a name="remarks"></a>Примечания  
 Этот метод аналогичен методу [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) за тем исключением, что он дополнительно получает доступ к переменным, добавленным в инструментарий ReJIT профилировщика. Установка `flags` для `ILCODE_ORIGINAL_IL` эквивалентно вызову [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md). Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.  
  
 Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: Практическое руководство](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
