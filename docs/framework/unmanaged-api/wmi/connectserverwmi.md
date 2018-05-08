---
title: Функция ConnectServerWmi (Справочник по неуправляемым API)
description: Функция ConnectServerWmi для создания подключения к пространству имен WMI использует DCOM.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de8447b9b090fc7f53df23346d61932bcb4dd6ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="connectserverwmi-function"></a>Функция ConnectServerWmi
Создает подключается через DCOM с пространством имен WMI на указанном компьютере.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a>Параметры

`strNetworkResource` [in] Указатель на допустимый `BSTR` , содержащее путь объекта правильное пространство имен WMI. В разделе [примечания](#remarks) Дополнительные сведения.

`strUser` [in] Указатель на допустимый `BSTR` , содержащее имя пользователя. Объект `null` значение указывает текущий контекст безопасности. Если пользователь находится в другом домене, отличную от текущей, `strUser` может также содержать имя домена и пользователя, разделенных обратной косой чертой. `strUser` может быть пользователь имя участника (UPN) отформатировать, suhc как *userName@domainName*. В разделе [примечания](#remarks) Дополнительные сведения.

`strPassword` [in] Указатель на допустимый `BSTR` , содержащее пароль. Объект `null` указывает текущий контекст безопасности. Пустая строка ("») указывает допустимый пароль нулевой длины.

`strLocale` [in] Указатель на допустимый `BSTR` указывает нужный языковой стандарт для извлечения данных. Для кодов языка Microsoft имеет формат строки «MS\_*xxx*», где *xxx* — это строка в шестнадцатеричном формате, который указывает идентификатор языка (LCID). Если указан недопустимый код языка, метод возвращает `WBEM_E_INVALID_PARAMETER` в Windows 7, где вместо него используется язык сервера по умолчанию, за исключением. Если "используется null1 текущего языкового стандарта. 
 
`lSecurityFlags` [in] Флаги для передачи `ConnectServerWmi` метод. Приводит значение нуль (0) для этого параметра в вызове `ConnectServerWmi` возвращение только после установления соединения с сервером. Это может привести к приложению, не отвечает бесконечно Если сервер будет нарушена. Другими допустимыми значениями являются:

| Константа  | Значение  | Описание  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Зарезервировано для внутреннего использования. Не используется. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi` Возвращает более двух минут. |

`strAuthority` [in] Имя домена пользователя. Возможны следующие значения:

| Значение | Описание |
|---------|---------|
| пустая | Используется проверка подлинности NTLM и используется домен NTLM текущего пользователя. Если `strUser` указывает домен (рекомендуемое расположение), не должны указываться здесь. Функция возвращает `WBEM_E_INVALID_PARAMETER` при указании домена в обоих параметров. |
| Kerberos:*имя участника* | Используется проверка подлинности Kerberos, и этот параметр содержит имя участника Kerberos. |
| NTLMDOMAIN:*имя домена* | Используется проверка подлинности NT LAN Manager, и этот параметр содержит доменное имя NTLM. |

`pCtx`   
[in] Как правило, этот параметр не является `null`. В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) объекта требуется один или несколько поставщиков динамического класса. 

`ppNamespace`  
[out] При возврате функция получает указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) объект привязан к указанным пространством имен. Ему присваивается пункты `null` при наличии ошибки.

`impLevel`  
[in] Уровень олицетворения.

`authLevel`  
[in] Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) метод.

 Для локального доступа к пространству имен по умолчанию `strNetworkResource` может быть путем простого объекта: «root\default» или «\\.\root\default». Для доступа к пространству имен по умолчанию на удаленном компьютере с помощью COM или Microsoft совместимых сетей, включают имя компьютера: «\\myserver\root\default». Имя компьютера также может быть DNS-имя или IP-адрес. `ConnectServerWmi` Функции можно также подключиться, и на компьютерах с IPv6 с помощью IPv6-адрес.

`strUser` не может быть пустой строкой. Если домен указан в `strAuthority`, он не также должно быть включено в `strUser`, или функция возвращает `WBEM_E_INVALID_PARAMETER`.


## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
