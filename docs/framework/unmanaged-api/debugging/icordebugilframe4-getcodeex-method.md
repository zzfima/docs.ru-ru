---
title: Метод ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb50459e36cfeb76a0c9a1e1cd4544260d484f45
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926795"
---
# <a name="icordebugilframe4getcodeex-method"></a>Метод ICorDebugILFrame4::GetCodeEx
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает указатель на код, который выполняется этим кадром стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `flags`  
 окне Элемент перечисления [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) , указывающий, включается ли в кадр промежуточный язык (IL), определенный в запросе ReJIT профилировщика.  
  
 `ppCode`  
 заполняет Указатель на адрес объекта ICorDebugCode, который представляет код, который исполняется этим кадром стека.  
  
## <a name="remarks"></a>Примечания  
 Этот метод аналогичен методу [ICorDebugFrame::-Code](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) , за исключением того, что он дополнительно получает доступ к коду, определенному в запросе ReJIT профилировщика. Вызов этого метода со `flags` `ILCODE_ORIGINAL_IL` значением эквивалентен вызову метода " [."](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)если метод инструментирован, его Il будет недоступен. `ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика. Если IL не инструментирован, `ppCode` имеет **значение NULL**и метод возвращает. `S_OK`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT Руководство](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
