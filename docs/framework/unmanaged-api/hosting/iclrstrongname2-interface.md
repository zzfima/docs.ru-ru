---
title: Интерфейс ICLRStrongName2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrstrongname2-interface"></a>Интерфейс ICLRStrongName2
Предоставляет возможность создавать с помощью группы SHA-2 (SHA-256, SHA-384 и SHA-512) хэш-алгоритмов Secure строгие имена.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод StrongNameGetPublicKeyEx](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|Возвращает открытый ключ из пары открытого и закрытого ключей и указывает хэш-алгоритм и алгоритм подписи.|  
|[Метод StrongNameSignatureVerificationEx2](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|Проверяет подпись сборки строгим именем, а также сопоставление ключ ECMA действительный ключ.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
