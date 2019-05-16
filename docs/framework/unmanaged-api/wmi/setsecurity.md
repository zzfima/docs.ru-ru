---
title: Функция SetSecurity (Справочник по неуправляемым API)
description: Функция SetSecurity получает маркер олицетворения текущего потока.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cecd8538b8f2b5d04cb9f1822751661ce9f8728
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636221"
---
# <a name="setsecurity-function"></a>Функция SetSecurity

Получает маркер олицетворения, связанный с текущим потоком. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a>Параметры

`pNeedToReset`\
[out] При возврате функции, содержит указатель на `boolean` , указывающее, следует ли сбросить маркер путем вызова [ResetSecurity](resetsecurity.md) функции.

`token`\
[out] При возврате функции, содержит указатель на дескриптор токена олицетворения, связанный с текущим потоком. Его значение может быть `null` имеется ли токен, не связанный с текущим потоком. 

## <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).

Если функция завершается с ошибкой, возвращается код ошибки. Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования

 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** WMINet_Utils.idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
