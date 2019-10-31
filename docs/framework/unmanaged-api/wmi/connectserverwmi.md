---
title: Функция Коннектсервервми (Справочник по неуправляемым API)
description: Функция Коннектсервервми использует DCOM для создания соединения с пространством имен WMI.
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
ms.openlocfilehash: 25a73060ed242fd0e77042cd0ea9618b9b27250f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128694"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="ed64a-103">Функция Коннектсервервми</span><span class="sxs-lookup"><span data-stu-id="ed64a-103">ConnectServerWmi function</span></span>

<span data-ttu-id="ed64a-104">Создает подключение через DCOM к пространству имен WMI на указанном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed64a-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ed64a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed64a-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="ed64a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed64a-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="ed64a-107">окне Указатель на допустимый `BSTR`, содержащий путь к объекту для правильного пространства имен WMI.</span><span class="sxs-lookup"><span data-stu-id="ed64a-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="ed64a-108">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="ed64a-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="ed64a-109">окне Указатель на допустимое `BSTR`, содержащее имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed64a-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="ed64a-110">Значение `null` указывает текущий контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed64a-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="ed64a-111">Если пользователь находится в домене, отличном от домена текущего, `strUser` может также содержать домен и имя пользователя, разделенные обратной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="ed64a-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="ed64a-112">`strUser` также может быть в формате имени участника-пользователя (UPN), например `userName@domainName`.</span><span class="sxs-lookup"><span data-stu-id="ed64a-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="ed64a-113">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="ed64a-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="ed64a-114">окне Указатель на допустимое `BSTR`, содержащее пароль.</span><span class="sxs-lookup"><span data-stu-id="ed64a-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="ed64a-115">`null` указывает текущий контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed64a-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="ed64a-116">Пустая строка ("") указывает действительный пароль нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="ed64a-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="ed64a-117">окне Указатель на допустимое `BSTR`, указывающий правильный языковой стандарт для извлечения сведений.</span><span class="sxs-lookup"><span data-stu-id="ed64a-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="ed64a-118">Для идентификаторов языкового стандарта Майкрософт формат строки — "MS\_*xxx*", где *xxx* — строка в шестнадцатеричном формате, которая указывает код локали (LCID).</span><span class="sxs-lookup"><span data-stu-id="ed64a-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="ed64a-119">Если указан недопустимый языковой стандарт, метод возвращает `WBEM_E_INVALID_PARAMETER`, за исключением Windows 7, где используется языковой стандарт по умолчанию сервера.</span><span class="sxs-lookup"><span data-stu-id="ed64a-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="ed64a-120">Если значение равно "NULL1", используется текущий языковой стандарт.</span><span class="sxs-lookup"><span data-stu-id="ed64a-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="ed64a-121">окне Флаги, передаваемые в метод `ConnectServerWmi`.</span><span class="sxs-lookup"><span data-stu-id="ed64a-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="ed64a-122">Значение, равное нулю (0) для этого параметра, приводит к вызову `ConnectServerWmi` возврате только после установления соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="ed64a-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="ed64a-123">Это может привести к тому, что приложение не будет реагировать на неопределенное время, если сервер не работает.</span><span class="sxs-lookup"><span data-stu-id="ed64a-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="ed64a-124">Другие допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="ed64a-124">The other valid values are:</span></span>

| <span data-ttu-id="ed64a-125">Константа</span><span class="sxs-lookup"><span data-stu-id="ed64a-125">Constant</span></span>  | <span data-ttu-id="ed64a-126">значения</span><span class="sxs-lookup"><span data-stu-id="ed64a-126">Value</span></span>  | <span data-ttu-id="ed64a-127">Описание</span><span class="sxs-lookup"><span data-stu-id="ed64a-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="ed64a-128">0x40</span><span class="sxs-lookup"><span data-stu-id="ed64a-128">0x40</span></span> | <span data-ttu-id="ed64a-129">Зарезервировано для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ed64a-129">Reserved for internal use.</span></span> <span data-ttu-id="ed64a-130">Не используется.</span><span class="sxs-lookup"><span data-stu-id="ed64a-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="ed64a-131">0x80</span><span class="sxs-lookup"><span data-stu-id="ed64a-131">0x80</span></span> | <span data-ttu-id="ed64a-132">`ConnectServerWmi` возвращают не более двух минут.</span><span class="sxs-lookup"><span data-stu-id="ed64a-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="ed64a-133">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed64a-133">[in] The domain name of the user.</span></span> <span data-ttu-id="ed64a-134">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ed64a-134">It can have the following values:</span></span>

| <span data-ttu-id="ed64a-135">значения</span><span class="sxs-lookup"><span data-stu-id="ed64a-135">Value</span></span> | <span data-ttu-id="ed64a-136">Описание</span><span class="sxs-lookup"><span data-stu-id="ed64a-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="ed64a-137">пустая</span><span class="sxs-lookup"><span data-stu-id="ed64a-137">blank</span></span> | <span data-ttu-id="ed64a-138">Используется проверка подлинности NTLM, и используется домен NTLM текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="ed64a-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="ed64a-139">Если `strUser` указывает домен (рекомендуемое расположение), его не следует указывать здесь.</span><span class="sxs-lookup"><span data-stu-id="ed64a-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="ed64a-140">Функция возвращает `WBEM_E_INVALID_PARAMETER`, если домен указан в обоих параметрах.</span><span class="sxs-lookup"><span data-stu-id="ed64a-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="ed64a-141">Kerberos:*имя участника*</span><span class="sxs-lookup"><span data-stu-id="ed64a-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="ed64a-142">Используется проверка подлинности Kerberos, и этот параметр содержит имя участника Kerberos.</span><span class="sxs-lookup"><span data-stu-id="ed64a-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="ed64a-143">НТЛМДОМАИН:*доменное имя*</span><span class="sxs-lookup"><span data-stu-id="ed64a-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="ed64a-144">Используется проверка подлинности NT LAN Manager, и этот параметр содержит доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="ed64a-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="ed64a-145">окне Как правило, этот параметр имеет `null`.</span><span class="sxs-lookup"><span data-stu-id="ed64a-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="ed64a-146">В противном случае он является указателем на объект [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , необходимый одному или нескольким динамическим поставщикам классов.</span><span class="sxs-lookup"><span data-stu-id="ed64a-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="ed64a-147">заполняет При возврате функции получает указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , привязанный к указанному пространству имен.</span><span class="sxs-lookup"><span data-stu-id="ed64a-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="ed64a-148">Он указывает на `null` при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed64a-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="ed64a-149">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="ed64a-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="ed64a-150">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="ed64a-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="ed64a-151">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed64a-151">Return value</span></span>

<span data-ttu-id="ed64a-152">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ed64a-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ed64a-153">Константа</span><span class="sxs-lookup"><span data-stu-id="ed64a-153">Constant</span></span>  |<span data-ttu-id="ed64a-154">значения</span><span class="sxs-lookup"><span data-stu-id="ed64a-154">Value</span></span>  |<span data-ttu-id="ed64a-155">Описание</span><span class="sxs-lookup"><span data-stu-id="ed64a-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ed64a-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ed64a-156">0x80041001</span></span> | <span data-ttu-id="ed64a-157">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="ed64a-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ed64a-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ed64a-158">0x80041008</span></span> | <span data-ttu-id="ed64a-159">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="ed64a-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ed64a-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ed64a-160">0x80041006</span></span> | <span data-ttu-id="ed64a-161">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="ed64a-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ed64a-162">0</span><span class="sxs-lookup"><span data-stu-id="ed64a-162">0</span></span> | <span data-ttu-id="ed64a-163">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ed64a-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ed64a-164">Заметки</span><span class="sxs-lookup"><span data-stu-id="ed64a-164">Remarks</span></span>

<span data-ttu-id="ed64a-165">Эта функция заключает в оболочку вызов метода [ивбемлокатор:: коннектсервер](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) .</span><span class="sxs-lookup"><span data-stu-id="ed64a-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="ed64a-166">Для локального доступа к пространству имен по умолчанию `strNetworkResource` может быть простым путем к объекту: "root\default" или "\\.\рут\дефаулт".</span><span class="sxs-lookup"><span data-stu-id="ed64a-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="ed64a-167">Для доступа к пространству имен по умолчанию на удаленном компьютере, использующем COM или совместимую с корпорацией Майкрософт сеть, укажите имя компьютера: "\\мисервер\рут\дефаулт".</span><span class="sxs-lookup"><span data-stu-id="ed64a-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="ed64a-168">Имя компьютера также может быть DNS-именем или IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="ed64a-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="ed64a-169">Функция `ConnectServerWmi` также может подключаться к компьютерам с IPv6 с помощью IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="ed64a-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="ed64a-170">`strUser` не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="ed64a-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="ed64a-171">Если домен указан в `strAuthority`, он также не должен включаться в `strUser`или функция возвращает `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="ed64a-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed64a-172">Требования</span><span class="sxs-lookup"><span data-stu-id="ed64a-172">Requirements</span></span>

 <span data-ttu-id="ed64a-173">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed64a-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ed64a-174">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ed64a-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="ed64a-175">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed64a-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ed64a-176">См. также</span><span class="sxs-lookup"><span data-stu-id="ed64a-176">See also</span></span>

- [<span data-ttu-id="ed64a-177">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="ed64a-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
