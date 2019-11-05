---
title: Функция Креатеинстанцеенумвми (Справочник по неуправляемым API)
description: Функция Креатеинстанцеенумвми Возвращает перечислитель, содержащий экземпляры указанного класса, соответствующие критериям выбора.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9ffa718be0e8b67471fdf8cb277df201388d2840
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130401"
---
# <a name="createinstanceenumwmi-function"></a>Функция Креатеинстанцеенумвми

Возвращает перечислитель, возвращающий экземпляры указанного класса в соответствии с заданными критериями выбора.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a>Параметры

`strFilter`\
окне Имя класса, для которого нужны экземпляры. Этот параметр не может быть `null`.

`lFlags`\
окне Сочетание флагов, влияющих на поведение этой функции. Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Если параметр задан, функция получает измененные квалификаторы, хранящиеся в локализованном пространстве имен языкового стандарта текущего соединения. <br/> Если значение не задано, функция извлекает только квалификаторы, хранящиеся в пространстве имен immediate. |
| `WBEM_FLAG_DEEP` | 0 | Перечисление включает в себя этот и все подклассы в иерархии. |
| `WBEM_FLAG_SHALLOW` | 1 | Перечисление включает только чистые экземпляры этого класса и исключает все экземпляры подклассов, которые предоставляют свойства, не найденные в этом классе. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Флаг вызывает вызов семисинчронаус. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Функция возвращает перечислитель только для перенаправления. Как правило, перечислители выполняются быстрее и используют меньше памяти, чем обычные перечислители, но не допускают вызовы для [клонирования](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | Инструментарий WMI удерживает указатели на объекты в перечислении до их освобождения. |

Для лучшей производительности рекомендуется использовать флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY`.

`pCtx`\
окне Как правило, это значение `null`. В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные экземпляры.

`ppEnum`\
заполняет Получает указатель на перечислитель.

`authLevel`\
окне Уровень авторизации.

`impLevel`\
окне Уровень олицетворения.

`pCurrentNamespace`\
окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , представляющий текущее пространство имен.

`strUser`\
окне Имя пользователя. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

`strPassword`\
окне Пароль. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

`strAuthority`\
окне Доменное имя пользователя. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | У пользователя нет разрешения на просмотр экземпляров указанного класса. |
| `WBEM_E_FAILED` | 0x80041001 | Произошла неопределенная ошибка. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strFilter` — не существует. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Вероятно, Инструментарий WMI остановлен и перезапущен. Снова вызовите [коннектсервервми](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Заметки

Эта функция заключает вызов метода [IWbemServices:: креатеклассенум](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) .

Обратите внимание, что возвращаемый перечислитель может иметь нулевые элементы.

Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** WMINet_Utils. idl

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
