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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93cae803b42d80dc0f868e2189de442eedea43f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186372"
---
# <a name="icordebugthread4getblockingobjects-method"></a>Метод ICorDebugThread4::GetBlockingObjects
Предоставляет перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) сведения о блокировании потока структуры, обеспечивающие.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Параметры  
 `ppBlockingObjectEnum`  
 [out] Указатель на перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.  
  
## <a name="remarks"></a>Примечания  
 Первый элемент в возвращаемом перечислении соответствует Первая структура, блокирующий поток. Второй элемент соответствует элементу блокировки, выдаваемое во время выполнения асинхронный вызов процедур (APC) при блокировке в первую и т. д.  
  
 Перечисление является допустимым только в течение текущего синхронизированного состояния.  
  
 Этот метод должен вызываться, пока отлаживаемый объект находится в синхронизированном состоянии.  
  
 Если `ppBlockingObjectEnum` не является допустимым указателем, результат не определен.  
  
 Если ошибку не удается определить поток заблокирован, метод возвращает значение HRESULT, указывающее на сбой; в противном случае возвращается значение S_OK.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
