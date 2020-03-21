---
title: Функция GetObjectText (Неуправляемая ссылка на API)
description: Функция GetObjectText возвращает текстовую визуализацию объекта в синтаксисе MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176790"
---
# <a name="getobjecttext-function"></a>Функция GetObjectText
Возвращает текстовую визуализацию объекта в синтаксисе Управляемого объекта (MOF).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
(в) Обычно 0. Если `WBEM_FLAG_NO_FLAVORS` (или 0x1) указан, квалификаторы включаются без распространения или информации о вкусе.

`pstrObjectText`(ваут) Указатель `null` на вход. В ответ недавно `BSTR` выделенное, содержащее синтаксис MOF, рендеризирующее объект.  

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недействительный параметр. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для выполнения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::GetObjectText.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)

Ответный текст MOF не содержит всю информацию об объекте, но только достаточно информации для компилятора MOF, чтобы иметь возможность воссоздать исходный объект. Например, не включены распространяемые квалификаторы или свойства родительского класса.

Для реконструкции текста параметров метода используется следующий алгоритм:

1. Параметры ресекризируются в порядке значений идентификатора.
1. Параметры, которые указаны как `[in]` и `[out]` объединены в единый параметр.

`pstrObjectText`должен быть указателем `null` на то, когда функция называется; он не должен указывать на строку, действительную до вызова метода, потому что указатель не будет расположен.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
