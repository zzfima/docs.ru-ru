---
title: Функция CloneEnumWbemClassObject (Неуправляемая справка API)
description: Функция CloneEnumWbemClassObject является логической копией регистратора.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175022"
---
# <a name="cloneenumwbemclassobject-function"></a>Функция CloneEnumWbemClassObject
Создает логическую копию перечислителя, сохраняя текущую позицию в перечислении.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a>Параметры

`ppEnum`\
(ваут) Получает указатель на новый [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
(в) Уровень авторизации.

`impLevel`\
(в) Уровень олицетворения.

`pCurrentEnumWbemClassObject`\
(ваут) Указатель на экземпляр [IEnumWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) который будет клонирован.

`strUser`\
(в) Имя пользователя. Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)

`strPassword`\
(в) Пароль. Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)

`strAuthority`\
(в) Доменное имя пользователя. Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр недействителен. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти доступно завершить операцию. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Соединение удаленной процедуры (RPC) между текущим процессом и WMI не удалось. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |

## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IEnumWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)

Этот метод делает только "лучшее усилие" копию. Из-за динамического характера многих объектов CIM, возможно, что новый регистратор не перечисляет тот же набор объектов, что и исходный регистратор.

Если вызов функции не удается, вы можете получить дополнительную информацию об ошибке, позвонив в функцию [GetErrorInfo.](geterrorinfo.md)

## <a name="example"></a>Пример

Например, [см.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)

## <a name="requirements"></a>Требования
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** WMINet_Utils.idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
