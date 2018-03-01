---
title: "Функция ClrCreateManagedInstance"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64a1bc6bbd89e3a36ac53b322bb246a7e61baa67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreatemanagedinstance-function"></a>Функция ClrCreateManagedInstance
Создает экземпляр указанного управляемого типа.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Используйте активации COM для создания экземпляра управляемого типа или размещения (в разделе [CLR размещение интерфейсов, добавленные в платформу .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pTypeName`  
 [in] Указатель на имя запрашиваемого типа экземпляра.  
  
 `riid`  
 [in] `IID` Запрашиваемого типа экземпляра.  
  
 `ppObject`  
 [out] Указатель на указатель на экземпляр управляемого типа, который был запрошен вызывающим объектом.  
  
## <a name="remarks"></a>Примечания  
 Общеязыковая среда выполнения уже должна быть загружена в процесс. Например, его можно загрузить с помощью вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции перед `ClrCreateManagedInstance` функция. Если среда выполнения не загружается, `ClrCreateManagedInstance` сначала пытается загрузить v1.0.3705 среды выполнения. В случае неудачи пытается загрузить последнюю версию среды выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
