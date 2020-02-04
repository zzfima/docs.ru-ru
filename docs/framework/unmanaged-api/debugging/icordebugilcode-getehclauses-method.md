---
title: Метод ICorDebugILCode::GetEHClauses
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: ac9a4e4b54b302afeae4ede1dd574c15ded3ff12
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788603"
---
# <a name="icordebugilcodegetehclauses-method"></a>Метод ICorDebugILCode::GetEHClauses
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Возвращает указатель на список предложений обработки исключений, определенных для этого промежуточного языка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cClauses`  
 [в] Емкость хранилища массива `clauses`. Дополнительные сведения см. в разделе «Примечания».  
  
 `pcClauses`  
 [из] Количество предложений, информация о которых записывается в массив `clauses`.  
  
 предложения  
 заполняет Массив объектов [кордебужехклаусе](cordebugehclause-structure.md) , содержащих сведения о предложениях обработки исключений, определенных для этого IL.  
  
## <a name="remarks"></a>Заметки  
 Если `cClauses` имеет значение 0, а `pcClauses` не равно**null**, `pcClauses` задается число доступных предложений обработки исключений. Если значение `cClauses` не равно 0, оно обозначает емкость хранилища массива `clauses`. Когда метод возвращает не пустое значение, `clauses` содержит максимум элементов `cClauses`, а значению `pcClauses` присваивается количество предложений, записанных в массив `clauses` на данный момент.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)
- [Структура CorDebugEHClause](cordebugehclause-structure.md)
- [Интерфейсы отладки](debugging-interfaces.md)
