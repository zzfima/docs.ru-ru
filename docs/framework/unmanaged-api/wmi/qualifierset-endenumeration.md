---
title: Функция QualifierSet_EndEnumeration (Справочник по неуправляемым API)
description: Функция QualifierSet_EndEnumeration завершает перечисление.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5a817174ec4c4e4407c19bb1d6d2d852d86dd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798321"
---
# <a name="qualifierset_endenumeration-function"></a>Функция QualifierSet_EndEnumeration
Завершает перечисление, начатое вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`   
окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

## <a name="return-value"></a>Возвращаемое значение

Следующее значение, возвращаемое этой функцией, определено в файле заголовка *вбемкли. h* , или его можно определить как константу в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .

Этот вызов рекомендуется, но не является обязательным. Он немедленно освобождает ресурсы, связанные с перечислением.

## <a name="requirements"></a>Требования  

**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
**Заголовок.** WMINet_Utils. idl  
  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
