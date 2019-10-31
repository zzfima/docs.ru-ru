---
title: Метод ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: e4d5582b7a3df16db58ea0ed001dcbffcdcaab79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122453"
---
# <a name="icordebugthread4getblockingobjects-method"></a>Метод ICorDebugThread4::GetBlockingObjects
Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Параметры  
 `ppBlockingObjectEnum`  
 заполняет Указатель на упорядоченное перечисление структур [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .  
  
## <a name="remarks"></a>Заметки  
 Первый элемент в возвращенном перечислении соответствует первой структуре, блокирующей поток. Второй элемент соответствует блокирующему элементу, который обнаруживается при выполнении асинхронного вызова процедуры (APC) при блокировке в первом и т. д.  
  
 Перечисление допустимо только в течение текущего синхронизированного состояния.  
  
 Этот метод должен вызываться, когда отлаживаемый объект находится в синхронизированном состоянии.  
  
 Если `ppBlockingObjectEnum` не является допустимым указателем, результат не определен.  
  
 Если поток заблокирован и ошибка не может быть определена, метод возвращает значение HRESULT, указывающее на ошибку; в противном случае возвращается значение S_OK.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
