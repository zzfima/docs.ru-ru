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
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178784"
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
 (в) Участник [пересчета ILCodeKind,](ilcodekind-enumeration.md) который определяет, включен ли в кадр промежуточный язык (IL), определяемый запросом ReJIT профайлера.  
  
 `ppCode`  
 (ваут) Указатель на адрес объекта "ICorDebugCode", представляющий код, который исполняется в этом стека.  
  
## <a name="remarks"></a>Remarks  
 Этот метод аналогичен методу [ICorDebugFrame::GetCode,](icordebugframe-getcode-method.md) за исключением того, что он дополнительно получает доступ к коду, определенному запросом ReJIT профайлера. Вызов этого метода `flags` `ILCODE_ORIGINAL_IL` со значением эквивалентно вызову [GetCode;](icordebugframe-getcode-method.md) если метод инструментальный, его IL не будет доступен. `ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика. Если IL не инструментальный, `ppCode` является **недействительным,** `S_OK`и метод возвращается .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [ReJIT: Как-к руководству](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
