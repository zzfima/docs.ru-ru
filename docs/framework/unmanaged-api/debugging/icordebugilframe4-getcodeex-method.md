---
title: "Метод ICorDebugILFrame4::GetCodeEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc80882353bd7a9861f4db79b83493d1cef7bfee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 [in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) член перечисления, указывающее, включается ли в кадре промежуточного языка (IL), определенному запросом ReJIT профилировщика.  
  
 `ppCode`  
 [out] Указатель на адрес объекта «ICorDebugCode», который представляет код, который выполняется этим кадром стека.  
  
## <a name="remarks"></a>Примечания  
 Этот метод аналогичен [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) за исключением того, что он дополнительно получает доступ к коду, определенному запросом ReJIT профилировщика. Вызов этого метода с `flags` значение `ILCODE_ORIGINAL_IL` эквивалентно вызову [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Если этот метод инструментирован, его IL станут недоступны. `ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика. Если промежуточный язык не инструментирован, `ppCode` — **null**, а метод возвращает `S_OK`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Практические руководства](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
