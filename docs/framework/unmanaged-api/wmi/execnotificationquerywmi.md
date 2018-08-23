---
title: Функция ExecNotificationQueryWmi (Справочник по неуправляемым API)
description: Функция ExecNotificationQueryWmi выполняет запрос для получения событий.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d314d85e7c1297636e8dd5cecaf050a527151518
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754590"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="fb7be-103">Функция ExecNotificationQueryWmi</span><span class="sxs-lookup"><span data-stu-id="fb7be-103">ExecNotificationQueryWmi function</span></span>
<span data-ttu-id="fb7be-104">Выполняет запрос для получения событий.</span><span class="sxs-lookup"><span data-stu-id="fb7be-104">Executes a query to receive events.</span></span> <span data-ttu-id="fb7be-105">Вызов возвращается немедленно, а вызывающий объект может опросить возвращенном перечислителе для событий, при их поступлении.</span><span class="sxs-lookup"><span data-stu-id="fb7be-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="fb7be-106">Освобождение возвращенном перечислителе отменяет запрос.</span><span class="sxs-lookup"><span data-stu-id="fb7be-106">Releasing the returned enumerator cancels the query.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fb7be-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb7be-107">Syntax</span></span>  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

## <a name="parameters"></a><span data-ttu-id="fb7be-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb7be-108">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="fb7be-109">[in] Строка с допустимым запросом язык, поддерживаемый управления Windows.</span><span class="sxs-lookup"><span data-stu-id="fb7be-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="fb7be-110">Оно должно быть «WQL», сокращение для языка запросов WMI.</span><span class="sxs-lookup"><span data-stu-id="fb7be-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="fb7be-111">[in] Текст запроса.</span><span class="sxs-lookup"><span data-stu-id="fb7be-111">[in] The text of the query.</span></span> <span data-ttu-id="fb7be-112">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="fb7be-112">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="fb7be-113">[in] Комбинация из следующих двух флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="fb7be-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="fb7be-114">Эти значения определены в *WbemCli.h* файл заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="fb7be-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> 

| <span data-ttu-id="fb7be-115">Константа</span><span class="sxs-lookup"><span data-stu-id="fb7be-115">Constant</span></span> | <span data-ttu-id="fb7be-116">Значение</span><span class="sxs-lookup"><span data-stu-id="fb7be-116">Value</span></span>  | <span data-ttu-id="fb7be-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="fb7be-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="fb7be-118">0x10</span><span class="sxs-lookup"><span data-stu-id="fb7be-118">0x10</span></span> | <span data-ttu-id="fb7be-119">Этот флаг приводит к Полусинхронный вызов.</span><span class="sxs-lookup"><span data-stu-id="fb7be-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="fb7be-120">Если этот флаг не установлен, вызов завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fb7be-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="fb7be-121">Это обусловлено их получения постоянно, это означает, что пользователь должен опросить возвращенном перечислителе.</span><span class="sxs-lookup"><span data-stu-id="fb7be-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="fb7be-122">Блокирует этот вызов бесконечно делает, невозможно.</span><span class="sxs-lookup"><span data-stu-id="fb7be-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="fb7be-123">0x20</span><span class="sxs-lookup"><span data-stu-id="fb7be-123">0x20</span></span> | <span data-ttu-id="fb7be-124">Функция возвращает только вперед перечислителя.</span><span class="sxs-lookup"><span data-stu-id="fb7be-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="fb7be-125">Обычно перечислители только вперед, выполняются быстрее и использовать меньше памяти, чем обычные перечислители, но они не допускают вызовы [клона](clone.md).</span><span class="sxs-lookup"><span data-stu-id="fb7be-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`  
<span data-ttu-id="fb7be-126">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="fb7be-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="fb7be-127">В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) экземпляр, который может использоваться поставщиком, предоставляющего запрошенные события.</span><span class="sxs-lookup"><span data-stu-id="fb7be-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span> 

`ppEnum`  
<span data-ttu-id="fb7be-128">[out] При отсутствии ошибок, получающей указатель на перечислитель, который позволяет вызывающей стороне для получения экземпляров в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="fb7be-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="fb7be-129">См. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="fb7be-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="fb7be-130">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="fb7be-130">[in] The authorization level.</span></span>

<span data-ttu-id="fb7be-131">`impLevel` [in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="fb7be-131">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="fb7be-132">[in] Указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объект, представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fb7be-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="fb7be-133">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb7be-133">[in] The user name.</span></span> <span data-ttu-id="fb7be-134">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="fb7be-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="fb7be-135">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="fb7be-135">[in] The password.</span></span> <span data-ttu-id="fb7be-136">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="fb7be-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="fb7be-137">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb7be-137">[in] The domain name of the user.</span></span> <span data-ttu-id="fb7be-138">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="fb7be-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="fb7be-139">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb7be-139">Return value</span></span>

<span data-ttu-id="fb7be-140">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="fb7be-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fb7be-141">Константа</span><span class="sxs-lookup"><span data-stu-id="fb7be-141">Constant</span></span>  |<span data-ttu-id="fb7be-142">Значение</span><span class="sxs-lookup"><span data-stu-id="fb7be-142">Value</span></span>  |<span data-ttu-id="fb7be-143">Описание:</span><span class="sxs-lookup"><span data-stu-id="fb7be-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="fb7be-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="fb7be-144">0x80041003</span></span> | <span data-ttu-id="fb7be-145">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть.</span><span class="sxs-lookup"><span data-stu-id="fb7be-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="fb7be-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fb7be-146">0x80041001</span></span> | <span data-ttu-id="fb7be-147">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fb7be-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fb7be-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fb7be-148">0x80041008</span></span> | <span data-ttu-id="fb7be-149">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="fb7be-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="fb7be-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="fb7be-150">0x80041010</span></span> | <span data-ttu-id="fb7be-151">Запрос указывает класс, который не существует.</span><span class="sxs-lookup"><span data-stu-id="fb7be-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="fb7be-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="fb7be-152">0x80042002</span></span> | <span data-ttu-id="fb7be-153">Запрошено слишком много точности в доставку событий.</span><span class="sxs-lookup"><span data-stu-id="fb7be-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="fb7be-154">Должно быть указано больше погрешность опроса.</span><span class="sxs-lookup"><span data-stu-id="fb7be-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="fb7be-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="fb7be-155">0x80042001</span></span> | <span data-ttu-id="fb7be-156">Requess запросов, которые можно предоставить больше информации, чем управления Windows.</span><span class="sxs-lookup"><span data-stu-id="fb7be-156">The query requess more information than Windows Management can provide.</span></span> <span data-ttu-id="fb7be-157">Это `HRESULT` возвращается при запросе событий приводит к запросу, чтобы опросить все объекты в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="fb7be-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="fb7be-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="fb7be-158">0x80041017</span></span> | <span data-ttu-id="fb7be-159">Запрос содержит синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="fb7be-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="fb7be-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="fb7be-160">0x80041018</span></span> | <span data-ttu-id="fb7be-161">Запрошенный язык запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fb7be-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="fb7be-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="fb7be-162">0x8004106c</span></span> | <span data-ttu-id="fb7be-163">Запрос является слишком сложным.</span><span class="sxs-lookup"><span data-stu-id="fb7be-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fb7be-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fb7be-164">0x80041006</span></span> | <span data-ttu-id="fb7be-165">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="fb7be-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="fb7be-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="fb7be-166">0x80041033</span></span> | <span data-ttu-id="fb7be-167">WMI был, вероятно, остановлена или перезапустить.</span><span class="sxs-lookup"><span data-stu-id="fb7be-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="fb7be-168">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="fb7be-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="fb7be-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="fb7be-169">0x80041015</span></span> | <span data-ttu-id="fb7be-170">Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="fb7be-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="fb7be-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="fb7be-171">0x80041058</span></span> | <span data-ttu-id="fb7be-172">Невозможно проанализировать запрос.</span><span class="sxs-lookup"><span data-stu-id="fb7be-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fb7be-173">0</span><span class="sxs-lookup"><span data-stu-id="fb7be-173">0</span></span> | <span data-ttu-id="fb7be-174">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="fb7be-174">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fb7be-175">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb7be-175">Remarks</span></span>

<span data-ttu-id="fb7be-176">Эта функция создает оболочку для вызова [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) метод.</span><span class="sxs-lookup"><span data-stu-id="fb7be-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="fb7be-177">После возврата функции, вызывающий объект периодически передает возвращенного `ppEnum` объект [Далее](next.md) функцию, чтобы увидеть, если все события будут доступны.</span><span class="sxs-lookup"><span data-stu-id="fb7be-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="fb7be-178">Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL.</span><span class="sxs-lookup"><span data-stu-id="fb7be-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="fb7be-179">Большое количество WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки в виде `HRESULT` значение.</span><span class="sxs-lookup"><span data-stu-id="fb7be-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="fb7be-180">Ограничение ключевых слов WQL зависит от того, насколько сложным является запрос.</span><span class="sxs-lookup"><span data-stu-id="fb7be-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="fb7be-181">Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="fb7be-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb7be-182">Требования</span><span class="sxs-lookup"><span data-stu-id="fb7be-182">Requirements</span></span>  
 <span data-ttu-id="fb7be-183">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb7be-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7be-184">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fb7be-184">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fb7be-185">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7be-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7be-186">См. также</span><span class="sxs-lookup"><span data-stu-id="fb7be-186">See also</span></span>  
[<span data-ttu-id="fb7be-187">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fb7be-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
