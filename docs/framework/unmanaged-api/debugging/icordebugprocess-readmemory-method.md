---
title: Метод ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: dca2a4e5ee869346108137a8ba01ab8855756725
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792557"
---
# <a name="icordebugprocessreadmemory-method"></a>Метод ICorDebugProcess::ReadMemory
Считывает указанную область памяти для этого процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 окне Значение `CORDB_ADDRESS`, указывающее базовый адрес памяти для чтения.  
  
 `size`  
 окне Число байтов, считываемых из памяти.  
  
 `buffer`  
 заполняет Буфер, который получает содержимое памяти.  
  
 `read`  
 заполняет Указатель на число байтов, передаваемых в указанный буфер.  
  
## <a name="remarks"></a>Заметки  
 Метод `ReadMemory` в основном предназначен для использования в отладке взаимодействия для проверки областей памяти, используемых неуправляемой частью отлаживаемого кода. Этот метод также можно использовать для считывания кода на языке MSIL и собственного JIT-скомпилированного кода.  
  
 Все управляемые точки останова будут удалены из данных, возвращаемых в параметре `buffer`. Никакие изменения для собственных точек останова, заданных [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md), не выполняются.  
  
 Кэширование памяти процесса не выполняется.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
