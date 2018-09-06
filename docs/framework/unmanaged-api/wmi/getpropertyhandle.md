---
title: Функция GetPropertyHandle (Справочник по неуправляемым API)
description: Функция GetPropertyHandle возвращает уникальный дескриптор этого свойства удостоверения.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94171b0708c97eb7510e916e451ed03645d706f3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877915"
---
# <a name="getpropertyhandle-function"></a>Функция GetPropertyHandle
Возвращает уникальный маркер, определяющий свойство.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) экземпляра.

`wszPropertyName`  
[in] Завершающаяся нулем строка кодировке UTF16 знака, содержащее имя свойства.   

`pType`  
[out] Указатель на [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) член перечисления, представляющее тип CIM данного свойства.

`pHandle`   
[out] Указатель на целое число, которое содержит дескриптор свойства.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Свойство с указанным именем не найден. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Запрошенное свойство имеет тип, `CIM_OBJECT` или `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) метод.

Вы можете использовать этот дескриптор для идентификации свойств, при использовании [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) методы для чтения или записи значения свойств.

Дескрипторы может быть извлечен для свойства всех типов данных, отличных от `CIM_OBJECT` и `CIM_ARRAY`. Возвращаемые дескрипторы работы для всех экземпляров класса.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
