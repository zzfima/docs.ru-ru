---
title: Функция CreateCoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 0b210f105495fa3f5595adbcb0805e1d1fb62310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179219"
---
# <a name="createcoreclrdebugtarget-function"></a>Функция CreateCoreClrDebugTarget
Создает подключение к прокси-серверу отладчика, который работает на удаленной машине, и возвращает объект [ICoreClrDebugTarget,](icoreclrdebugtarget-interface.md) который может быть использован для запроса запущенных процессов и загруженных времен выполнения на удаленной машине.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwAddress`  
 [in] IPv4-адрес удаленного целевого компьютера.  
  
 `ppTarget`  
 (ваут) Указатель на указатель на объект [ICoreClrDebugTarget,](icoreclrdebugtarget-interface.md) который будет создан.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.  
  
 E_OUTOFMEMORY  
 Не удается выделить достаточно памяти для `ppTarget`.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Рамочные версии .NET:** 3.5 SP1
