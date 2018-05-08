---
title: Перечисление HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fce759877ad5e3c9041344647781da07ad19a45a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Запустите приложение от AppLaunch.exe.<br /><br /> Это значение можно используйте для приложений с частичным доверием.|  
|`HOST_TYPE_CORFLAG`|Запустите приложение непосредственно. То есть запустите приложение из свой собственный файл .exe.<br /><br /> Это значение можно используйте для приложений с полным доверием.|  
|`HOST_TYPE_DEFAULT`|То же, как HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
