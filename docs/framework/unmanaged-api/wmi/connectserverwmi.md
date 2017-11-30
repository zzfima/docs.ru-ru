---
title: "Функция ConnectServerWmi (Справочник по неуправляемым API)"
description: "Функция ConnectServerWmi для создания подключения к пространству имен WMI использует DCOM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ConnectServerWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ConnectServerWmi
helpviewer_keywords: ConnectServerWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b51050bce4603ebcfe99fb38d66e54683c677293
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="e2dad-103">Функция ConnectServerWmi</span><span class="sxs-lookup"><span data-stu-id="e2dad-103">ConnectServerWmi function</span></span>
<span data-ttu-id="e2dad-104">Создает подключается через DCOM с пространством имен WMI на указанном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e2dad-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e2dad-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2dad-105">Syntax</span></span>  
  
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
## <a name="parameters"></a><span data-ttu-id="e2dad-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2dad-106">Parameters</span></span>

<span data-ttu-id="e2dad-107">`strNetworkResource`[in] Указатель на допустимый `BSTR` , содержащее путь объекта правильное пространство имен WMI.</span><span class="sxs-lookup"><span data-stu-id="e2dad-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="e2dad-108">В разделе [примечания](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="e2dad-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="e2dad-109">`strUser`[in] Указатель на допустимый `BSTR` , содержащее имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2dad-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="e2dad-110">Объект `null` значение указывает текущий контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="e2dad-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="e2dad-111">Если пользователь находится в другом домене, отличную от текущей, `strUser` может также содержать имя домена и пользователя, разделенных обратной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="e2dad-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="e2dad-112">`strUser`может быть пользователь имя участника (UPN) отформатировать, suhc как  *userName@domainName* .</span><span class="sxs-lookup"><span data-stu-id="e2dad-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="e2dad-113">В разделе [примечания](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="e2dad-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="e2dad-114">`strPassword`[in] Указатель на допустимый `BSTR` , содержащее пароль.</span><span class="sxs-lookup"><span data-stu-id="e2dad-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="e2dad-115">Объект `null` указывает текущий контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="e2dad-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="e2dad-116">Пустая строка ("») указывает допустимый пароль нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="e2dad-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="e2dad-117">`strLocale`[in] Указатель на допустимый `BSTR` указывает нужный языковой стандарт для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="e2dad-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="e2dad-118">Для кодов языка Microsoft имеет формат строки «MS\_*xxx*», где *xxx* — это строка в шестнадцатеричном формате, который указывает идентификатор языка (LCID).</span><span class="sxs-lookup"><span data-stu-id="e2dad-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="e2dad-119">Если указан недопустимый код языка, метод возвращает `WBEM_E_INVALID_PARAMETER` в Windows 7, где вместо него используется язык сервера по умолчанию, за исключением.</span><span class="sxs-lookup"><span data-stu-id="e2dad-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="e2dad-120">Если "используется null1 текущего языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="e2dad-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="e2dad-121">`lSecurityFlags`[in] Флаги для передачи `ConnectServerWmi` метод.</span><span class="sxs-lookup"><span data-stu-id="e2dad-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="e2dad-122">Приводит значение нуль (0) для этого параметра в вызове `ConnectServerWmi` возвращение только после установления соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="e2dad-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="e2dad-123">Это может привести к приложению, не отвечает бесконечно Если сервер будет нарушена.</span><span class="sxs-lookup"><span data-stu-id="e2dad-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="e2dad-124">Другими допустимыми значениями являются:</span><span class="sxs-lookup"><span data-stu-id="e2dad-124">The other valid values are:</span></span>

| <span data-ttu-id="e2dad-125">Константа</span><span class="sxs-lookup"><span data-stu-id="e2dad-125">Constant</span></span>  | <span data-ttu-id="e2dad-126">Значение</span><span class="sxs-lookup"><span data-stu-id="e2dad-126">Value</span></span>  | <span data-ttu-id="e2dad-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e2dad-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="e2dad-128">0x40</span><span class="sxs-lookup"><span data-stu-id="e2dad-128">0x40</span></span> | <span data-ttu-id="e2dad-129">Зарезервировано для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="e2dad-129">Reserved for internal use.</span></span> <span data-ttu-id="e2dad-130">Не используется.</span><span class="sxs-lookup"><span data-stu-id="e2dad-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="e2dad-131">0x80</span><span class="sxs-lookup"><span data-stu-id="e2dad-131">0x80</span></span> | <span data-ttu-id="e2dad-132">`ConnectServerWmi`Возвращает более двух минут.</span><span class="sxs-lookup"><span data-stu-id="e2dad-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="e2dad-133">`strAuthority`[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2dad-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="e2dad-134">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e2dad-134">It can have the following values:</span></span>

| <span data-ttu-id="e2dad-135">Значение</span><span class="sxs-lookup"><span data-stu-id="e2dad-135">Value</span></span> | <span data-ttu-id="e2dad-136">Описание</span><span class="sxs-lookup"><span data-stu-id="e2dad-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="e2dad-137">пустая</span><span class="sxs-lookup"><span data-stu-id="e2dad-137">blank</span></span> | <span data-ttu-id="e2dad-138">Используется проверка подлинности NTLM и используется домен NTLM текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2dad-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="e2dad-139">Если `strUser` указывает домен (рекомендуемое расположение), не должны указываться здесь.</span><span class="sxs-lookup"><span data-stu-id="e2dad-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="e2dad-140">Функция возвращает `WBEM_E_INVALID_PARAMETER` при указании домена в обоих параметров.</span><span class="sxs-lookup"><span data-stu-id="e2dad-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="e2dad-141">Kerberos:*имя участника*</span><span class="sxs-lookup"><span data-stu-id="e2dad-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="e2dad-142">Используется проверка подлинности Kerberos, и этот параметр содержит имя участника Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e2dad-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="e2dad-143">NTLMDOMAIN:*имя домена*</span><span class="sxs-lookup"><span data-stu-id="e2dad-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="e2dad-144">Используется проверка подлинности NT LAN Manager, и этот параметр содержит доменное имя NTLM.</span><span class="sxs-lookup"><span data-stu-id="e2dad-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="e2dad-145">[in] Как правило, этот параметр не является `null`.</span><span class="sxs-lookup"><span data-stu-id="e2dad-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="e2dad-146">В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) объекта требуется один или несколько поставщиков динамического класса.</span><span class="sxs-lookup"><span data-stu-id="e2dad-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="e2dad-147">[out] При возврате функция получает указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) объект привязан к указанным пространством имен.</span><span class="sxs-lookup"><span data-stu-id="e2dad-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="e2dad-148">Ему присваивается пункты `null` при наличии ошибки.</span><span class="sxs-lookup"><span data-stu-id="e2dad-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="e2dad-149">[in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="e2dad-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="e2dad-150">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="e2dad-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="e2dad-151">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2dad-151">Return value</span></span>

<span data-ttu-id="e2dad-152">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e2dad-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e2dad-153">Константа</span><span class="sxs-lookup"><span data-stu-id="e2dad-153">Constant</span></span>  |<span data-ttu-id="e2dad-154">Значение</span><span class="sxs-lookup"><span data-stu-id="e2dad-154">Value</span></span>  |<span data-ttu-id="e2dad-155">Описание</span><span class="sxs-lookup"><span data-stu-id="e2dad-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="e2dad-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e2dad-156">0x80041001</span></span> | <span data-ttu-id="e2dad-157">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="e2dad-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e2dad-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e2dad-158">0x80041008</span></span> | <span data-ttu-id="e2dad-159">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="e2dad-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e2dad-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e2dad-160">0x80041006</span></span> | <span data-ttu-id="e2dad-161">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="e2dad-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e2dad-162">0</span><span class="sxs-lookup"><span data-stu-id="e2dad-162">0</span></span> | <span data-ttu-id="e2dad-163">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="e2dad-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e2dad-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2dad-164">Remarks</span></span>

<span data-ttu-id="e2dad-165">Эта функция создает оболочку для вызова [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="e2dad-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="e2dad-166">Для локального доступа к пространству имен по умолчанию `strNetworkResource` может быть путем простого объекта: «root\default» или «\\.\root\default».</span><span class="sxs-lookup"><span data-stu-id="e2dad-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="e2dad-167">Для доступа к пространству имен по умолчанию на удаленном компьютере с помощью COM или Microsoft совместимых сетей, включают имя компьютера: «\\myserver\root\default».</span><span class="sxs-lookup"><span data-stu-id="e2dad-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="e2dad-168">Имя компьютера также может быть DNS-имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="e2dad-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="e2dad-169">`ConnectServerWmi` Функции можно также подключиться, и на компьютерах с IPv6 с помощью IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="e2dad-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="e2dad-170">`strUser`не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="e2dad-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="e2dad-171">Если домен указан в `strAuthority`, он не также должно быть включено в `strUser`, или функция возвращает `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="e2dad-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="e2dad-172">Требования</span><span class="sxs-lookup"><span data-stu-id="e2dad-172">Requirements</span></span>  
 <span data-ttu-id="e2dad-173">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2dad-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2dad-174">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e2dad-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e2dad-175">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e2dad-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2dad-176">См. также</span><span class="sxs-lookup"><span data-stu-id="e2dad-176">See also</span></span>  
[<span data-ttu-id="e2dad-177">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e2dad-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
