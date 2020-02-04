---
title: Интерфейс ICorDebugModule3
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
ms.openlocfilehash: 33acc4d9a0819c43d17c362fcbea2e7636521fd3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792936"
---
# <a name="icordebugmodule3-interface"></a>Интерфейс ICorDebugModule3
Создает средство чтения символов для динамического модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorDebugModule3::CreateReaderForInMemorySymbols](icordebugmodule3-createreaderforinmemorysymbols-method.md)|Создает средство чтения символов (обычно [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.|  
  
## <a name="remarks"></a>Заметки  
 Этот интерфейс логически расширяет интерфейсы "ICorDebugModule" и "ICorDebugModule2".  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 4,5, 4, 3,5 SP1
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)

- [Интерфейсы отладки](debugging-interfaces.md)
