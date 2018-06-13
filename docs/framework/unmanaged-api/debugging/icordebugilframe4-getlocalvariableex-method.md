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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a82f092a0f10fd621ac4facdee201fa239e1c1b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414533"
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
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 [in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) член перечисления, указывающее, включается ли в кадр переменная, добавленная в инструментарий ReJIT профилировщика.  
  
 `dwIndex`  
 [в] Индекс локальной переменной в кадре стека промежуточного языка.  
  
 `ppValue`  
 [out] Указатель на адрес объекта, представляющего извлеченное значение «ICorDebugValue».  
  
## <a name="remarks"></a>Примечания  
 Этот метод аналогичен [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) за исключением того, что он дополнительно получает доступ к переменной, добавленной в инструментарий ReJIT профилировщика. Вызов этого метода с `flags` значение `ILCODE_ORIGINAL_IL` эквивалентно вызову [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); Если этот метод инструментирован с дополнительными локальными переменными, эти переменные не доступны. `ILCODE_REJIT_IL` обеспечивает отладчику доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика. Если промежуточный язык не инструментирован, метод возвращает значение `E_INVALIDARG`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Практические руководства](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
