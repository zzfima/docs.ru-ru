---
title: Функция InitDbgTransportManager
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948e97064d12dc5b2044faf35aa374e5ba5f2592
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764781"
---
# <a name="initdbgtransportmanager-function"></a>Функция InitDbgTransportManager
Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Выполнено.  
  
 E_OUTOFMEMORY  
 Функции не удалось выделить память для диспетчера транспорта.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)
