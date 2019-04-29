---
title: Функция ExecQueryWmi (Справочник по неуправляемым API)
description: Функция ExecQueryWmi выполняет запрос для извлечения объектов.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 402bbcb9ad5e462a55c5ec2716417f512f03ee19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609065"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="ef541-103">Функция ExecQueryWmi</span><span class="sxs-lookup"><span data-stu-id="ef541-103">ExecQueryWmi function</span></span>

<span data-ttu-id="ef541-104">Выполняет запрос для получения объектов.</span><span class="sxs-lookup"><span data-stu-id="ef541-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ef541-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef541-105">Syntax</span></span>

```cpp
HRESULT ExecQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="ef541-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef541-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="ef541-107">[in] Строка с допустимым запросом язык, поддерживаемый управления Windows.</span><span class="sxs-lookup"><span data-stu-id="ef541-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="ef541-108">Оно должно быть «WQL», сокращение для языка запросов WMI.</span><span class="sxs-lookup"><span data-stu-id="ef541-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="ef541-109">[in] Текст запроса.</span><span class="sxs-lookup"><span data-stu-id="ef541-109">[in] The text of the query.</span></span> <span data-ttu-id="ef541-110">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="ef541-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="ef541-111">[in] Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="ef541-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="ef541-112">Следующие значения определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ef541-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="ef541-113">Константа</span><span class="sxs-lookup"><span data-stu-id="ef541-113">Constant</span></span> | <span data-ttu-id="ef541-114">Значение</span><span class="sxs-lookup"><span data-stu-id="ef541-114">Value</span></span>  | <span data-ttu-id="ef541-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ef541-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="ef541-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="ef541-116">0x20000</span></span> | <span data-ttu-id="ef541-117">Если набор, функция извлекает измененные квалификаторы, хранящиеся в локализованных имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="ef541-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="ef541-118">В противном случае набор, функция получает только квалификаторы, хранящихся в пространство имен немедленно.</span><span class="sxs-lookup"><span data-stu-id="ef541-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="ef541-119">0x10</span><span class="sxs-lookup"><span data-stu-id="ef541-119">0x10</span></span> | <span data-ttu-id="ef541-120">Этот флаг приводит к Полусинхронный вызов.</span><span class="sxs-lookup"><span data-stu-id="ef541-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="ef541-121">0x20</span><span class="sxs-lookup"><span data-stu-id="ef541-121">0x20</span></span> | <span data-ttu-id="ef541-122">Функция возвращает только вперед перечислителя.</span><span class="sxs-lookup"><span data-stu-id="ef541-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="ef541-123">Обычно перечислители только вперед, выполняются быстрее и использовать меньше памяти, чем обычные перечислители, но они не допускают вызовы [клона](clone.md).</span><span class="sxs-lookup"><span data-stu-id="ef541-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="ef541-124">0</span><span class="sxs-lookup"><span data-stu-id="ef541-124">0</span></span> | <span data-ttu-id="ef541-125">WMI сохраняет указатели на объекты в перечислении, до их появления.</span><span class="sxs-lookup"><span data-stu-id="ef541-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="ef541-126">0x100</span><span class="sxs-lookup"><span data-stu-id="ef541-126">0x100</span></span> | <span data-ttu-id="ef541-127">Гарантирует, что все возвращаемые объекты имеют достаточно информации, в них, так что свойства системы, такие как **__PATH**, **__RELPATH**, и **__SERVER**, не являются `null`.</span><span class="sxs-lookup"><span data-stu-id="ef541-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="ef541-128">2</span><span class="sxs-lookup"><span data-stu-id="ef541-128">2</span></span> | <span data-ttu-id="ef541-129">Этот флаг используется для создания прототипов.</span><span class="sxs-lookup"><span data-stu-id="ef541-129">This flag is used for prototyping.</span></span> <span data-ttu-id="ef541-130">Он не выполняет запрос и возвращает объект, который выглядит как типичный результирующий объект.</span><span class="sxs-lookup"><span data-stu-id="ef541-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="ef541-131">0x200</span><span class="sxs-lookup"><span data-stu-id="ef541-131">0x200</span></span> | <span data-ttu-id="ef541-132">Причины прямой доступ к поставщику для класса, задается независимо от его родительского класса или его подклассов.</span><span class="sxs-lookup"><span data-stu-id="ef541-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="ef541-133">Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="ef541-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="ef541-134">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="ef541-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="ef541-135">В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы.</span><span class="sxs-lookup"><span data-stu-id="ef541-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="ef541-136">[out] При отсутствии ошибок, получающей указатель на перечислитель, который позволяет вызывающей стороне для получения экземпляров в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="ef541-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="ef541-137">Запрос может содержать результирующий набор с нуля экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ef541-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="ef541-138">См. в разделе ["Примечания"](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="ef541-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="ef541-139">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="ef541-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="ef541-140">[in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="ef541-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="ef541-141">[in] Указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объект, представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="ef541-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="ef541-142">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef541-142">[in] The user name.</span></span> <span data-ttu-id="ef541-143">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="ef541-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="ef541-144">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="ef541-144">[in] The password.</span></span> <span data-ttu-id="ef541-145">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="ef541-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="ef541-146">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef541-146">[in] The domain name of the user.</span></span> <span data-ttu-id="ef541-147">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="ef541-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ef541-148">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ef541-148">Return value</span></span>

<span data-ttu-id="ef541-149">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ef541-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ef541-150">Константа</span><span class="sxs-lookup"><span data-stu-id="ef541-150">Constant</span></span>  |<span data-ttu-id="ef541-151">Значение</span><span class="sxs-lookup"><span data-stu-id="ef541-151">Value</span></span>  |<span data-ttu-id="ef541-152">Описание</span><span class="sxs-lookup"><span data-stu-id="ef541-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="ef541-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="ef541-153">0x80041003</span></span> | <span data-ttu-id="ef541-154">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть.</span><span class="sxs-lookup"><span data-stu-id="ef541-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="ef541-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ef541-155">0x80041001</span></span> | <span data-ttu-id="ef541-156">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ef541-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ef541-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ef541-157">0x80041008</span></span> | <span data-ttu-id="ef541-158">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="ef541-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="ef541-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="ef541-159">0x80041017</span></span> | <span data-ttu-id="ef541-160">Запрос содержит синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="ef541-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="ef541-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="ef541-161">0x80041018</span></span> | <span data-ttu-id="ef541-162">Запрошенный язык запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ef541-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="ef541-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="ef541-163">0x8004106c</span></span> | <span data-ttu-id="ef541-164">Запрос является слишком сложным.</span><span class="sxs-lookup"><span data-stu-id="ef541-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ef541-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ef541-165">0x80041006</span></span> | <span data-ttu-id="ef541-166">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="ef541-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="ef541-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="ef541-167">0x80041033</span></span> | <span data-ttu-id="ef541-168">WMI был, вероятно, остановлена или перезапустить.</span><span class="sxs-lookup"><span data-stu-id="ef541-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="ef541-169">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="ef541-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ef541-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ef541-170">0x80041015</span></span> | <span data-ttu-id="ef541-171">Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="ef541-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="ef541-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ef541-172">0x80041002</span></span> | <span data-ttu-id="ef541-173">Запрос указывает класс, который не существует.</span><span class="sxs-lookup"><span data-stu-id="ef541-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ef541-174">0</span><span class="sxs-lookup"><span data-stu-id="ef541-174">0</span></span> | <span data-ttu-id="ef541-175">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="ef541-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ef541-176">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef541-176">Remarks</span></span>

<span data-ttu-id="ef541-177">Эта функция создает оболочку для вызова [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) метод.</span><span class="sxs-lookup"><span data-stu-id="ef541-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="ef541-178">Эта функция обрабатывает запрос, указанный в `strQuery` параметр и создает перечислитель, который вызывающая сторона обеспечивает доступ к результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="ef541-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="ef541-179">Перечислитель — это указатель на [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) интерфейс; запроса результаты являются экземплярами типов объектов классов, которые предоставляются с помощью [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ef541-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="ef541-180">Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL.</span><span class="sxs-lookup"><span data-stu-id="ef541-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="ef541-181">Большое количество WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки в виде `HRESULT` значение.</span><span class="sxs-lookup"><span data-stu-id="ef541-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="ef541-182">Ограничение ключевых слов WQL зависит от того, насколько сложным является запрос.</span><span class="sxs-lookup"><span data-stu-id="ef541-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="ef541-183">Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="ef541-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef541-184">Требования</span><span class="sxs-lookup"><span data-stu-id="ef541-184">Requirements</span></span>

<span data-ttu-id="ef541-185">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef541-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ef541-186">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ef541-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ef541-187">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ef541-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ef541-188">См. также</span><span class="sxs-lookup"><span data-stu-id="ef541-188">See also</span></span>

- [<span data-ttu-id="ef541-189">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="ef541-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)