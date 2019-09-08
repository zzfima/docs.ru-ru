---
title: Функция Сетсекурити (Справочник по неуправляемым API)
description: Функция Сетсекурити Извлекает токен олицетворения текущего потока.
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
ms.openlocfilehash: 94c76213acb66116105d181e9961a33976047ee7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798248"
---
# <a name="setsecurity-function"></a>Функция Сетсекурити

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
заполняет При возврате функции содержит указатель на `boolean` , указывающий, следует ли сбрасывать маркер путем вызова функции [ресетсекурити](resetsecurity.md) .

`token`\
заполняет При возврате функции содержит указатель на маркер маркера олицетворения, связанный с текущим потоком. Его значение может быть `null` , если нет токена, связанного с текущим потоком. 

## <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение равно `S_OK` (0).

Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки. Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .

## <a name="requirements"></a>Требования

 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок.** WMINet_Utils. idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
