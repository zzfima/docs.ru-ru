---
title: Функция EndMethodEnumeration (Неуправляемая справка API)
description: Функция EndMethodEnumeration завершает последовательность перечисления метода.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175009"
---
# <a name="endmethodenumeration-function"></a>Функция EndMethodEnumeration
Прекращает перечисление последовательности, начатой с вызова к [функции BeginMethodEnumeration.](beginmethodenumeration.md)  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | 0x8004101d | Произошла внутренняя ошибка. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов [методом IWbemClassObject::EndMethodEnumeration.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)

Вызывающее запускает последовательность перечисления с помощью [функции BeginMethodEnumeration,](beginmethodenumeration.md) `WBEM_S_NO_MORE_DATA`а затем вызывает [функцию NextMethod](nextmethod.md )до тех пор, пока метод не вернется. Звонящее опционально завершает `EndMethodEnumeration`последовательность, позвонив. Звонящее может досрочно прекратить перечисление, позвонив `EndMethodEnumeration` в любое время.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
