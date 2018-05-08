---
title: Функция GetCurrentApartmentType (Справочник по неуправляемым API)
description: Функция GetCurrentApartmentType извлекает тип подразделения, в котором выполняется вызывающего объекта.
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
ms.openlocfilehash: ca7b5fa5bf6d845d542d3e80c0571e59f3d4c1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getcurrentapartmenttype-function"></a>Функция GetCurrentApartmentType
Возвращает тип подразделения, в котором выполняется вызывающего объекта.   
  
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
[in] Указатель на [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) экземпляра.

`aptType`  
[out] Указатель на [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) значение перечисления, указывающее подразделению вызывающей стороны.

## <a name="return-value"></a>Возвращаемое значение


|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `S_OK` | 0 | Выполнение функции было завершено успешно. |
| `E_FAIL` | 0x80000008 | Вызывающий объект не выполняется в подразделении. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
