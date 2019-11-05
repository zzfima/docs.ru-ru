---
title: Функция _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: b68f24908a5b214d507da8e8a4636a7c55259604
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123019"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a>\_ЕФН\_функция Жетманажедобжектфиелдинфо
Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `Client`  
 окне Указатель на клиент отладки.  
  
 `objAddr`  
 окне Указатель на управляемый объект.  
  
 сзфиелднаме  
 окне Указатель управляемого объекта на имя поля.  
  
 `pValue`  
 заполняет Значение поля. Этот параметр может быть нулевым.  
  
 `pOffset`  
 заполняет Смещение от `objAddr` к полю. Этот параметр может быть нулевым.  
  
## <a name="remarks"></a>Заметки  
 Если смещение равно 0, смещение не записывается.  
  
 Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE с значением устройства 0x82 и кодом ошибки 0x1000.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace. h  
  
 **Версия .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
