---
title: Указатель функции FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26b3de456bc28f51cb20ab72b3934041ec6b06ae
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490451"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a>Указатель функции FExecuteInAppDomainCallback
Указывает на функцию, которая вызывается средой выполнения (CLR) для выполнения управляемого кода.  
  
 Этот указатель функции был объявлен устаревшим в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cookie`  
 [in] Указатель на непрозрачные памяти, выделенный вызывающим объектом, содержащей управляемый код, который будет выполнен.  
  
 Вызывающий объект (CLR) управляет выделением и временем существования этой памяти. Это не памяти неуправляемой кучи среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** "Mscorwks.dll"  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
