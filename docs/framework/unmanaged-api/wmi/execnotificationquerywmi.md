---
title: Функция Ексекнотификатионкуеривми (Справочник по неуправляемым API)
description: Функция Ексекнотификатионкуеривми выполняет запрос для получения событий.
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
ms.openlocfilehash: 3d8a7683eef52a5e91bf7aa84d5aa7db7dbdac8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130441"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="0eff1-103">Функция ExecNotificationQueryWmi</span><span class="sxs-lookup"><span data-stu-id="0eff1-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="0eff1-104">Выполняет запрос для получения событий.</span><span class="sxs-lookup"><span data-stu-id="0eff1-104">Executes a query to receive events.</span></span> <span data-ttu-id="0eff1-105">Вызов возвращается немедленно, и вызывающий объект может опросить Возвращаемый перечислитель для событий по мере их поступления.</span><span class="sxs-lookup"><span data-stu-id="0eff1-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="0eff1-106">Освобождение возвращаемого перечислителя отменяет запрос.</span><span class="sxs-lookup"><span data-stu-id="0eff1-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0eff1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0eff1-107">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="0eff1-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="0eff1-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="0eff1-109">окне Строка с допустимым языком запросов, поддерживаемой службой управления Windows.</span><span class="sxs-lookup"><span data-stu-id="0eff1-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="0eff1-110">Оно должно быть "WQL", акронимом для язык запросов WMI.</span><span class="sxs-lookup"><span data-stu-id="0eff1-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="0eff1-111">окне Текст запроса.</span><span class="sxs-lookup"><span data-stu-id="0eff1-111">[in] The text of the query.</span></span> <span data-ttu-id="0eff1-112">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="0eff1-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="0eff1-113">окне Сочетание следующих двух флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="0eff1-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="0eff1-114">Эти значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="0eff1-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="0eff1-115">Константа</span><span class="sxs-lookup"><span data-stu-id="0eff1-115">Constant</span></span> | <span data-ttu-id="0eff1-116">значения</span><span class="sxs-lookup"><span data-stu-id="0eff1-116">Value</span></span>  | <span data-ttu-id="0eff1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0eff1-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="0eff1-118">0x10</span><span class="sxs-lookup"><span data-stu-id="0eff1-118">0x10</span></span> | <span data-ttu-id="0eff1-119">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="0eff1-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="0eff1-120">Если этот флаг не установлен, вызов завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0eff1-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="0eff1-121">Это связано с тем, что события получаются постоянно, что означает, что пользователь должен опросить возвращенный перечислитель.</span><span class="sxs-lookup"><span data-stu-id="0eff1-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="0eff1-122">Блокирование этого вызова бесконечно делает невозможным.</span><span class="sxs-lookup"><span data-stu-id="0eff1-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="0eff1-123">0x20</span><span class="sxs-lookup"><span data-stu-id="0eff1-123">0x20</span></span> | <span data-ttu-id="0eff1-124">Функция возвращает перечислитель только для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="0eff1-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="0eff1-125">Как правило, перечислители выполняются быстрее и используют меньше памяти, чем обычные перечислители, но не допускают вызовы для [клонирования](clone.md).</span><span class="sxs-lookup"><span data-stu-id="0eff1-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="0eff1-126">окне Как правило, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="0eff1-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="0eff1-127">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные события.</span><span class="sxs-lookup"><span data-stu-id="0eff1-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="0eff1-128">заполняет Если ошибка не возникает, получает указатель на перечислитель, позволяющий вызывающему объекту получить экземпляры в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="0eff1-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="0eff1-129">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="0eff1-130">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="0eff1-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="0eff1-131">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="0eff1-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="0eff1-132">окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="0eff1-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="0eff1-133">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="0eff1-133">[in] The user name.</span></span> <span data-ttu-id="0eff1-134">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="0eff1-135">окне Пароль.</span><span class="sxs-lookup"><span data-stu-id="0eff1-135">[in] The password.</span></span> <span data-ttu-id="0eff1-136">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="0eff1-137">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="0eff1-137">[in] The domain name of the user.</span></span> <span data-ttu-id="0eff1-138">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="0eff1-139">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0eff1-139">Return value</span></span>

<span data-ttu-id="0eff1-140">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="0eff1-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0eff1-141">Константа</span><span class="sxs-lookup"><span data-stu-id="0eff1-141">Constant</span></span>  |<span data-ttu-id="0eff1-142">значения</span><span class="sxs-lookup"><span data-stu-id="0eff1-142">Value</span></span>  |<span data-ttu-id="0eff1-143">Описание</span><span class="sxs-lookup"><span data-stu-id="0eff1-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="0eff1-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="0eff1-144">0x80041003</span></span> | <span data-ttu-id="0eff1-145">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые может возвращать функция.</span><span class="sxs-lookup"><span data-stu-id="0eff1-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="0eff1-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0eff1-146">0x80041001</span></span> | <span data-ttu-id="0eff1-147">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0eff1-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0eff1-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0eff1-148">0x80041008</span></span> | <span data-ttu-id="0eff1-149">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="0eff1-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="0eff1-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="0eff1-150">0x80041010</span></span> | <span data-ttu-id="0eff1-151">В запросе указан несуществующий класс.</span><span class="sxs-lookup"><span data-stu-id="0eff1-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="0eff1-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="0eff1-152">0x80042002</span></span> | <span data-ttu-id="0eff1-153">Запрошена слишком большая точность при доставке событий.</span><span class="sxs-lookup"><span data-stu-id="0eff1-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="0eff1-154">Необходимо указать более высокий допуск опроса.</span><span class="sxs-lookup"><span data-stu-id="0eff1-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="0eff1-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="0eff1-155">0x80042001</span></span> | <span data-ttu-id="0eff1-156">Запрос запрашивает больше информации, чем может предоставить система управления Windows.</span><span class="sxs-lookup"><span data-stu-id="0eff1-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="0eff1-157">Этот `HRESULT` возвращается, когда запрос события приводит к запросу на опрос всех объектов в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0eff1-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="0eff1-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="0eff1-158">0x80041017</span></span> | <span data-ttu-id="0eff1-159">В запросе возникла синтаксическая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0eff1-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="0eff1-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="0eff1-160">0x80041018</span></span> | <span data-ttu-id="0eff1-161">Запрошенный язык запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0eff1-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="0eff1-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="0eff1-162">0x8004106c</span></span> | <span data-ttu-id="0eff1-163">Запрос слишком сложен.</span><span class="sxs-lookup"><span data-stu-id="0eff1-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0eff1-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0eff1-164">0x80041006</span></span> | <span data-ttu-id="0eff1-165">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="0eff1-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="0eff1-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="0eff1-166">0x80041033</span></span> | <span data-ttu-id="0eff1-167">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="0eff1-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="0eff1-168">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0eff1-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0eff1-169">0x80041015</span></span> | <span data-ttu-id="0eff1-170">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="0eff1-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="0eff1-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="0eff1-171">0x80041058</span></span> | <span data-ttu-id="0eff1-172">Синтаксический анализ запроса невозможен.</span><span class="sxs-lookup"><span data-stu-id="0eff1-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0eff1-173">0</span><span class="sxs-lookup"><span data-stu-id="0eff1-173">0</span></span> | <span data-ttu-id="0eff1-174">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0eff1-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0eff1-175">Заметки</span><span class="sxs-lookup"><span data-stu-id="0eff1-175">Remarks</span></span>

<span data-ttu-id="0eff1-176">Эта функция заключает вызов метода [IWbemServices:: ексекнотификатионкуери](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="0eff1-177">После того как функция возвращает значение, вызывающий объект периодически передает возвращенный `ppEnum` объекта [следующей](next.md) функции, чтобы определить, доступны ли какие либо события.</span><span class="sxs-lookup"><span data-stu-id="0eff1-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="0eff1-178">Существует ряд ограничений на количество `AND` и `OR` ключевых слов, которые могут использоваться в запросах WQL.</span><span class="sxs-lookup"><span data-stu-id="0eff1-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="0eff1-179">Большое количество ключевых слов WQL, используемых в сложном запросе, может привести к тому, что инструментарий WMI возвратит `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки как значение `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0eff1-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="0eff1-180">Ограничение ключевых слов WQL зависит от того, насколько сложным является запрос.</span><span class="sxs-lookup"><span data-stu-id="0eff1-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="0eff1-181">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="0eff1-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0eff1-182">Требования</span><span class="sxs-lookup"><span data-stu-id="0eff1-182">Requirements</span></span>

<span data-ttu-id="0eff1-183">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eff1-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0eff1-184">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0eff1-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="0eff1-185">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0eff1-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0eff1-186">См. также</span><span class="sxs-lookup"><span data-stu-id="0eff1-186">See also</span></span>

- [<span data-ttu-id="0eff1-187">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="0eff1-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
