---
title: Функция Set Security (Неуправляемая справка API)
description: Функция SetSecurity извлекает токен олицетворения текущего потока.
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
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176738"
---
# <a name="setsecurity-function"></a>Функция SetSecurity

Получает маркер олицетворения, связанный с текущим потоком.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a>Параметры

`pNeedToReset`\
(ваут) При возврате функции содержится `boolean` указатель на указатель, указывающий, следует ли сбросить маркер, вызывая функцию [ResetSecurity.](resetsecurity.md)

`token`\
(ваут) Когда функция возвращается, содержит указатель на ручку маркера олицетворения, связанного с текущим потоком. Его значение `null` может быть, если нет маркера, связанного с текущим потоком.

## <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата `S_OK` (0).

Если функция выходит из строя, значение возврата является ненулевым кодом ошибки. Чтобы получить расширенную информацию об ошибке, позвоните в функцию [GetErrorInfo.](geterrorinfo.md)

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** WMINet_Utils.idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
