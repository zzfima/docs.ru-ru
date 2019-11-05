---
title: Функция LockClrVersion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133779"
---
# <a name="lockclrversion-function"></a>Функция LockClrVersion
Позволяет узлу определить, какая версия среды CLR будет использоваться в процессе перед явной инициализацией среды CLR.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hostCallback`  
 окне Функция, вызываемая средой CLR при инициализации.  
  
 `pBeginHostSetup`  
 окне Функция, вызываемая узлом для информирования среды CLR о начале инициализации.  
  
 `pEndHostSetup`  
 окне Функция, вызываемая узлом для информирования среды CLR о завершении инициализации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|Один или несколько аргументов имеют значение null.|  
  
## <a name="remarks"></a>Заметки  
 Узел вызывает `LockClrVersion` перед инициализацией среды CLR. `LockClrVersion` принимает три параметра, все из которых являются обратными вызовами типа [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Этот тип определяется следующим образом.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 При инициализации среды выполнения выполняются следующие действия.  
  
1. Узел вызывает [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или одну из других функций инициализации среды выполнения. Кроме того, узел может инициализировать среду выполнения с помощью активации объекта COM.  
  
2. Среда выполнения вызывает функцию, указанную параметром `hostCallback`.  
  
3. Функция, указанная `hostCallback`, затем выполняет следующую последовательность вызовов:  
  
    - Функция, заданная параметром `pBeginHostSetup`.  
  
    - `CorBindToRuntimeEx` (или другую функцию инициализации среды выполнения).  
  
    - [ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    - Функция, заданная параметром `pEndHostSetup`.  
  
 Все вызовы от `pBeginHostSetup` к `pEndHostSetup` должны выполняться в одном потоке или Fiber с одним и тем же логическим стеком. Этот поток может отличаться от потока, в котором вызывается `hostCallback`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
