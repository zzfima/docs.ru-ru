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
ms.openlocfilehash: ff9ea8cdc8aea66b1dd1f54c8be881882f6e27f7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611540"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="95a86-103">Функция ConnectServerWmi</span><span class="sxs-lookup"><span data-stu-id="95a86-103">ConnectServerWmi function</span></span>

<span data-ttu-id="95a86-104">Создает подключение через DCOM к пространству имен WMI на указанном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95a86-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="95a86-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95a86-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="95a86-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="95a86-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="95a86-107">[in] Указатель на допустимую `BSTR` , содержащий путь к объекту правильное пространство имен WMI.</span><span class="sxs-lookup"><span data-stu-id="95a86-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="95a86-108">См. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="95a86-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="95a86-109">[in] Указатель на допустимую `BSTR` , содержащий имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="95a86-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="95a86-110">Объект `null` значение указывает текущий контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="95a86-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="95a86-111">Если пользователь находится в другом домене, отличный от текущего, `strUser` может также содержать имя домена и пользователя, разделенные обратной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="95a86-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="95a86-112">`strUser` может также быть в формате имени участника (UPN) пользователя, например `userName@domainName`.</span><span class="sxs-lookup"><span data-stu-id="95a86-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="95a86-113">См. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="95a86-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="95a86-114">[in] Указатель на допустимую `BSTR` , содержащее пароль.</span><span class="sxs-lookup"><span data-stu-id="95a86-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="95a86-115">Объект `null` указывает текущий контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="95a86-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="95a86-116">Пустая строка ("») указывает допустимый пароль нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="95a86-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="95a86-117">[in] Указатель на допустимую `BSTR` указывает нужный языковой стандарт для получения сведений.</span><span class="sxs-lookup"><span data-stu-id="95a86-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="95a86-118">Для кодов языка Microsoft имеет следующий формат строки «MS\_*xxx*«, где *xxx* — это строка в шестнадцатеричной форме, указывающее идентификатор языка (LCID).</span><span class="sxs-lookup"><span data-stu-id="95a86-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="95a86-119">Если указан недопустимый код языка, метод возвращает `WBEM_E_INVALID_PARAMETER` кроме как на Windows 7, где вместо него используется локаль по умолчанию сервера.</span><span class="sxs-lookup"><span data-stu-id="95a86-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="95a86-120">Если "используется null1, текущий языковой стандарт.</span><span class="sxs-lookup"><span data-stu-id="95a86-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="95a86-121">[in] Флаги для передачи `ConnectServerWmi` метод.</span><span class="sxs-lookup"><span data-stu-id="95a86-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="95a86-122">Значение ноль (0) для этого параметра приводит к вызов `ConnectServerWmi` возвращение только после того, как установлено подключение к серверу.</span><span class="sxs-lookup"><span data-stu-id="95a86-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="95a86-123">В итоге приложение не отвечает на неопределенное время, является ли сервер работает.</span><span class="sxs-lookup"><span data-stu-id="95a86-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="95a86-124">Другими допустимыми значениями являются:</span><span class="sxs-lookup"><span data-stu-id="95a86-124">The other valid values are:</span></span>

| <span data-ttu-id="95a86-125">Константа</span><span class="sxs-lookup"><span data-stu-id="95a86-125">Constant</span></span>  | <span data-ttu-id="95a86-126">Значение</span><span class="sxs-lookup"><span data-stu-id="95a86-126">Value</span></span>  | <span data-ttu-id="95a86-127">Описание</span><span class="sxs-lookup"><span data-stu-id="95a86-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="95a86-128">0x40</span><span class="sxs-lookup"><span data-stu-id="95a86-128">0x40</span></span> | <span data-ttu-id="95a86-129">Зарезервировано для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="95a86-129">Reserved for internal use.</span></span> <span data-ttu-id="95a86-130">Не используется.</span><span class="sxs-lookup"><span data-stu-id="95a86-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="95a86-131">0x80</span><span class="sxs-lookup"><span data-stu-id="95a86-131">0x80</span></span> | <span data-ttu-id="95a86-132">`ConnectServerWmi` Возвращает за две минуты или меньше.</span><span class="sxs-lookup"><span data-stu-id="95a86-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="95a86-133">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="95a86-133">[in] The domain name of the user.</span></span> <span data-ttu-id="95a86-134">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="95a86-134">It can have the following values:</span></span>

| <span data-ttu-id="95a86-135">Значение</span><span class="sxs-lookup"><span data-stu-id="95a86-135">Value</span></span> | <span data-ttu-id="95a86-136">Описание</span><span class="sxs-lookup"><span data-stu-id="95a86-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="95a86-137">пустая</span><span class="sxs-lookup"><span data-stu-id="95a86-137">blank</span></span> | <span data-ttu-id="95a86-138">Используется проверка подлинности NTLM, и используется NTLM домен текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="95a86-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="95a86-139">Если `strUser` указывает домен (рекомендуемое расположение), не следует указывать здесь.</span><span class="sxs-lookup"><span data-stu-id="95a86-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="95a86-140">Функция возвращает `WBEM_E_INVALID_PARAMETER` при выборе домена в обоих параметрах.</span><span class="sxs-lookup"><span data-stu-id="95a86-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="95a86-141">Kerberos —*имя участника*</span><span class="sxs-lookup"><span data-stu-id="95a86-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="95a86-142">Используется проверка подлинности Kerberos, и этот параметр содержит имя участника Kerberos.</span><span class="sxs-lookup"><span data-stu-id="95a86-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="95a86-143">Значение NTLMDOMAIN:*доменное имя*</span><span class="sxs-lookup"><span data-stu-id="95a86-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="95a86-144">Используется проверка подлинности NT LAN Manager, и этот параметр содержит доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="95a86-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="95a86-145">[in] Как правило, этот параметр является `null`.</span><span class="sxs-lookup"><span data-stu-id="95a86-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="95a86-146">В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) объект, необходимый для одного или нескольких поставщиков динамического класса.</span><span class="sxs-lookup"><span data-stu-id="95a86-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="95a86-147">[out] Если функция возвращает, получает указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объект привязан к указанным пространством имен.</span><span class="sxs-lookup"><span data-stu-id="95a86-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="95a86-148">Ему будет присвоено пункты `null` при наличии ошибки.</span><span class="sxs-lookup"><span data-stu-id="95a86-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="95a86-149">[in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="95a86-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="95a86-150">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="95a86-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="95a86-151">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95a86-151">Return value</span></span>

<span data-ttu-id="95a86-152">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="95a86-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="95a86-153">Константа</span><span class="sxs-lookup"><span data-stu-id="95a86-153">Constant</span></span>  |<span data-ttu-id="95a86-154">Значение</span><span class="sxs-lookup"><span data-stu-id="95a86-154">Value</span></span>  |<span data-ttu-id="95a86-155">Описание</span><span class="sxs-lookup"><span data-stu-id="95a86-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="95a86-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="95a86-156">0x80041001</span></span> | <span data-ttu-id="95a86-157">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="95a86-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="95a86-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="95a86-158">0x80041008</span></span> | <span data-ttu-id="95a86-159">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="95a86-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="95a86-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="95a86-160">0x80041006</span></span> | <span data-ttu-id="95a86-161">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="95a86-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="95a86-162">0</span><span class="sxs-lookup"><span data-stu-id="95a86-162">0</span></span> | <span data-ttu-id="95a86-163">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="95a86-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="95a86-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="95a86-164">Remarks</span></span>

<span data-ttu-id="95a86-165">Эта функция создает оболочку для вызова [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) метод.</span><span class="sxs-lookup"><span data-stu-id="95a86-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="95a86-166">Для локального доступа к пространству имен по умолчанию `strNetworkResource` может быть путем простого объекта: «root\default» или "\\.\root\default».</span><span class="sxs-lookup"><span data-stu-id="95a86-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="95a86-167">Для доступа к пространству имен по умолчанию на удаленном компьютере с использованием сети, COM или совместимые с Microsoft, включают имя компьютера: "\\myserver\root\default».</span><span class="sxs-lookup"><span data-stu-id="95a86-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="95a86-168">Имя компьютера также может быть DNS-имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="95a86-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="95a86-169">`ConnectServerWmi` Функции можно также подключиться с компьютерами под управлением IPv6 с помощью IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="95a86-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="95a86-170">`strUser` не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="95a86-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="95a86-171">Если домен указан в `strAuthority`, он не также должно быть включено в `strUser`, или функция возвращает `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="95a86-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="95a86-172">Требования</span><span class="sxs-lookup"><span data-stu-id="95a86-172">Requirements</span></span>

 <span data-ttu-id="95a86-173">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95a86-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="95a86-174">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="95a86-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="95a86-175">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="95a86-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="95a86-176">См. также</span><span class="sxs-lookup"><span data-stu-id="95a86-176">See also</span></span>

- [<span data-ttu-id="95a86-177">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="95a86-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)