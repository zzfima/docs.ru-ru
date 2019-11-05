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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120217"
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
заполняет При возврате функции содержит указатель на `boolean`, указывающий, следует ли сбрасывать маркер путем вызова функции [ресетсекурити](resetsecurity.md) .

`token`\
заполняет При возврате функции содержит указатель на маркер маркера олицетворения, связанный с текущим потоком. Его значение может быть `null`, если нет токена, связанного с текущим потоком. 

## <a name="return-value"></a>Возвращаемое значение

Если функция выполнена удачно, возвращается значение `S_OK` (0).

Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки. Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** WMINet_Utils. idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
