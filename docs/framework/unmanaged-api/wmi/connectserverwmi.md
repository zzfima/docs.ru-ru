---
title: Функция ConnectServerWmi (Справочник по неуправляемым API)
description: Функция ConnectServerWmi использует DCOM для создания подключения к пространству имен WMI.
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
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45970427"
---
# <a name="connectserverwmi-function"></a>Функция ConnectServerWmi
Создает подключение через DCOM к пространству имен WMI на указанном компьютере.  
  
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

`strNetworkResource` [in] Указатель на допустимую `BSTR` , содержащий путь к объекту правильное пространство имен WMI. См. в разделе ["Примечания"](#remarks) Дополнительные сведения.

`strUser` [in] Указатель на допустимую `BSTR` , содержащий имя пользователя. Объект `null` значение указывает текущий контекст безопасности. Если пользователь находится в другом домене, отличный от текущего, `strUser` может также содержать имя домена и пользователя, разделенные обратной косой чертой. `strUser` может также быть в пользователя участника-пользователя (UPN) отформатировать, suhc как *userName@domainName*. См. в разделе ["Примечания"](#remarks) Дополнительные сведения.

`strPassword` [in] Указатель на допустимую `BSTR` , содержащее пароль. Объект `null` указывает текущий контекст безопасности. Пустая строка ("») указывает допустимый пароль нулевой длины.

`strLocale` [in] Указатель на допустимую `BSTR` указывает нужный языковой стандарт для получения сведений. Для кодов языка Microsoft имеет следующий формат строки «MS\_*xxx*«, где *xxx* — это строка в шестнадцатеричной форме, указывающее идентификатор языка (LCID). Если указан недопустимый код языка, метод возвращает `WBEM_E_INVALID_PARAMETER` кроме как на Windows 7, где вместо него используется локаль по умолчанию сервера. Если "используется null1, текущий языковой стандарт. 
 
`lSecurityFlags` [in] Флаги для передачи `ConnectServerWmi` метод. Значение ноль (0) для этого параметра приводит к вызов `ConnectServerWmi` возвращение только после того, как установлено подключение к серверу. В итоге приложение не отвечает на неопределенное время, является ли сервер работает. Другими допустимыми значениями являются:

| Константа  | Значение  | Описание  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Зарезервировано для внутреннего использования. Не используется. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi` Возвращает за две минуты или меньше. |

`strAuthority` [in] Имя домена пользователя. Возможны следующие значения:

| Значение | Описание |
|---------|---------|
| пустая | Используется проверка подлинности NTLM, и используется NTLM домен текущего пользователя. Если `strUser` указывает домен (рекомендуемое расположение), не следует указывать здесь. Функция возвращает `WBEM_E_INVALID_PARAMETER` при выборе домена в обоих параметрах. |
| Kerberos —*имя участника* | Используется проверка подлинности Kerberos, и этот параметр содержит имя участника Kerberos. |
| Значение NTLMDOMAIN:*доменное имя* | Используется проверка подлинности NT LAN Manager, и этот параметр содержит доменное имя NTLM. |

`pCtx`   
[in] Как правило, этот параметр является `null`. В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) объект, необходимый для одного или нескольких поставщиков динамического класса. 

`ppNamespace`  
[out] Если функция возвращает, получает указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объект привязан к указанным пространством имен. Ему будет присвоено пункты `null` при наличии ошибки.

`impLevel`  
[in] Уровень олицетворения.

`authLevel`  
[in] Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) метод.

 Для локального доступа к пространству имен по умолчанию `strNetworkResource` может быть путем простого объекта: «root\default» или "\\.\root\default». Для доступа к пространству имен по умолчанию на удаленном компьютере с использованием сети, COM или совместимые с Microsoft, включают имя компьютера: "\\myserver\root\default». Имя компьютера также может быть DNS-имя или IP-адрес. `ConnectServerWmi` Функции можно также подключиться с компьютерами под управлением IPv6 с помощью IPv6-адрес.

`strUser` не может быть пустой строкой. Если домен указан в `strAuthority`, он не также должно быть включено в `strUser`, или функция возвращает `WBEM_E_INVALID_PARAMETER`.


## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
