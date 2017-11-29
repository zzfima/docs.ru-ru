---
title: "Перечисление HOST_TYPE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: HOST_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: HOST_TYPE
helpviewer_keywords: HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e191293ff7bde6b1be2210af4e7830fec0d7290d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hosttype-enumeration"></a>Перечисление HOST_TYPE
Содержит значения, указывающие тип узла, которое запускает приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Запустите приложение от AppLaunch.exe.<br /><br /> Это значение можно используйте для приложений с частичным доверием.|  
|`HOST_TYPE_CORFLAG`|Запустите приложение непосредственно. То есть запустите приложение из свой собственный файл .exe.<br /><br /> Это значение можно используйте для приложений с полным доверием.|  
|`HOST_TYPE_DEFAULT`|То же, как HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
