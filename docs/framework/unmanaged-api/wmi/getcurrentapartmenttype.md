---
title: Функция GetCurrentApartmentType (Справочник по неуправляемым API)
description: Функция GetCurrentApartmentType извлекает тип апартамента, в котором выполняется вызывающий объект.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a999dc1850a41612f8896ff9a7ed96cd8c3a2fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509139"
---
# <a name="getcurrentapartmenttype-function"></a>Функция GetCurrentApartmentType
Получает тип подразделения, в котором выполняется вызывающий объект.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) экземпляра.

`aptType`  
[out] Указатель на [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) значение перечисления, указывающее подразделения вызывающей стороны.

## <a name="return-value"></a>Возвращаемое значение


|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `S_OK` | 0 | Функция успешно завершена. |
| `E_FAIL` | 0x80000008 | Вызывающий объект не выполняется в подразделении. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также
- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
