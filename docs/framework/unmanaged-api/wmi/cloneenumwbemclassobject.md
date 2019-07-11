---
title: Функция CloneEnumWbemClassObject (Справочник по неуправляемым API)
description: Функция CloneEnumWbemClassObject создается копия логического перечислитель.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab660769a49cf12b129cb7f44b8378053a231f8c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761625"
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
[out] Получает указатель на новый [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
[in] Уровень авторизации.

`impLevel`\
[in] Уровень олицетворения.

`pCurrentEnumWbemClassObject`\
[out] Указатель на [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) экземпляра для клонирования.

`strUser`\
[in] Имя пользователя. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

`strPassword`\
[in] Пароль. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

`strAuthority`\ [in] имя домена пользователя. См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти завершить операцию. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) метод.

Этот метод копирует только «оптимальных затрат». Из-за динамической природы множество объектов CIM вполне возможно, что новый перечислитель не перечислить тот же набор объектов, что перечислитель источника.

Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="example"></a>Пример

Например, см. в разделе [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) метод.

## <a name="requirements"></a>Требования
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

 **Заголовок.** WMINet_Utils.idl

 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
