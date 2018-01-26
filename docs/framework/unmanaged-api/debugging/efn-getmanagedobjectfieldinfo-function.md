---
title: "Функция _EFN_GetManagedObjectFieldInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectFieldInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectFieldInfo
helpviewer_keywords: _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4822cab8816e97bd1d13c36ea7b63dc9a6f679d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a>Функция _EFN_GetManagedObjectFieldInfo
Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `Client`  
 [in] Указатель на клиенте отладки.  
  
 `objAddr`  
 [in] Указатель на управляемый объект.  
  
 szFieldName  
 [in] Указатель на управляемый объект на имя поля.  
  
 `pValue`  
 [out] Значение поля. Этот параметр может быть нулевым.  
  
 `pOffset`  
 [out] Смещение от `objAddr` к полю. Этот параметр может быть нулевым.  
  
## <a name="remarks"></a>Примечания  
 Если смещение равно 0, смещение не записывается.  
  
 Если нет управляемого кода в потоке в данный момент в контексте, функция возвращает значение HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0xa0 и кодом ошибки 0x1000.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace.h  
  
 **Версия платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
