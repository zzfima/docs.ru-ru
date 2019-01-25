---
title: Функция QualifierSet_Put (Справочник по неуправляемым API)
description: Эта функция QualifierSet_Put записывает именованного квалификатора и его значение.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e1fc8d9d8c135f9eea8b9451b884ef3b7ba4704
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694143"
---
# <a name="qualifiersetput-function"></a>Функция QualifierSet_Put
Записывает именованный квалификатор и значение. Новый квалификатор перезаписывает предыдущее значение с тем же именем. Если квалификатор не существует, он создается. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`   
[in] Этот параметр не используется.

`ptr`   
[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.

`wszName`   
[in] Имя квалификатора для записи.

`pVal` [in] Указатель на допустимую `VARIANT` , содержащий квалификатор для записи. Этот параметр не может быть `null`.

`lFlavor` [in] Одно из следующих констант, который определяет требуемый квалификаторов для этот квалификатор. Значение по умолчанию — `WBEM_FLAVOR_OVERRIDABLE` (0).

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Квалификатор может переопределяться в производном классе или экземпляре. **Это значение по умолчанию.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Квалификатор распространяется в экземпляры. |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Квалификатор распространяется в производные классы. |
| "WBEM_FLAVOR_NOT_OVERRIDABLE | 0x10 | Квалификатор невозможно переопределить в производном классе или экземпляре. |
| "WBEM_FLAVOR_AMENDED | 0x80 | Квалификатор локализуется. |

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Возникла Недопустимая попытка указать **ключ** квалификатор для свойства, которое не может быть ключом. Ключи указываются om c; в группах доступности определение объекта и не могут быть изменены для каждого экземпляра. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | `pVal` Параметр не является типом квалификатора. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Невозможно вызвать `QualifierSet_Put` метод квалификатор, так как объект-владелец не разрешает переопределения. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также
- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
