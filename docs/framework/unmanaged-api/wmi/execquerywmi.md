---
title: Функция Ексеккуеривми (Справочник по неуправляемым API)
description: Функция Ексеккуеривми выполняет запрос для получения объектов.
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
ms.openlocfilehash: b8547d306819e85b838f1160d9912dd43e42f2f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798685"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="20243-103">Функция ExecQueryWmi</span><span class="sxs-lookup"><span data-stu-id="20243-103">ExecQueryWmi function</span></span>

<span data-ttu-id="20243-104">Выполняет запрос для получения объектов.</span><span class="sxs-lookup"><span data-stu-id="20243-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="20243-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20243-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="20243-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="20243-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="20243-107">окне Строка с допустимым языком запросов, поддерживаемой службой управления Windows.</span><span class="sxs-lookup"><span data-stu-id="20243-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="20243-108">Оно должно быть "WQL", акронимом для язык запросов WMI.</span><span class="sxs-lookup"><span data-stu-id="20243-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="20243-109">окне Текст запроса.</span><span class="sxs-lookup"><span data-stu-id="20243-109">[in] The text of the query.</span></span> <span data-ttu-id="20243-110">Этот параметр не может `null`быть.</span><span class="sxs-lookup"><span data-stu-id="20243-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="20243-111">окне Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="20243-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="20243-112">Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="20243-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="20243-113">Константа</span><span class="sxs-lookup"><span data-stu-id="20243-113">Constant</span></span> | <span data-ttu-id="20243-114">Значение</span><span class="sxs-lookup"><span data-stu-id="20243-114">Value</span></span>  | <span data-ttu-id="20243-115">Описание</span><span class="sxs-lookup"><span data-stu-id="20243-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="20243-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="20243-116">0x20000</span></span> | <span data-ttu-id="20243-117">Если параметр задан, функция получает измененные квалификаторы, хранящиеся в локализованном пространстве имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="20243-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="20243-118">Если значение не задано, функция извлекает только квалификаторы, хранящиеся в пространстве имен immediate.</span><span class="sxs-lookup"><span data-stu-id="20243-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="20243-119">0x10</span><span class="sxs-lookup"><span data-stu-id="20243-119">0x10</span></span> | <span data-ttu-id="20243-120">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="20243-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="20243-121">0x20</span><span class="sxs-lookup"><span data-stu-id="20243-121">0x20</span></span> | <span data-ttu-id="20243-122">Функция возвращает перечислитель только для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="20243-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="20243-123">Как правило, перечислители выполняются быстрее и используют меньше памяти, чем обычные перечислители, но не допускают вызовы для [клонирования](clone.md).</span><span class="sxs-lookup"><span data-stu-id="20243-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="20243-124">0</span><span class="sxs-lookup"><span data-stu-id="20243-124">0</span></span> | <span data-ttu-id="20243-125">Инструментарий WMI удерживает указатели на объекты в перечислении до их освобождения.</span><span class="sxs-lookup"><span data-stu-id="20243-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="20243-126">0x100</span><span class="sxs-lookup"><span data-stu-id="20243-126">0x100</span></span> | <span data-ttu-id="20243-127">Гарантирует, что все возвращенные объекты будут содержать достаточно информации, чтобы системные свойства, такие как **__Path**, **__RELPATH**и **__SERVER**, не `null`были.</span><span class="sxs-lookup"><span data-stu-id="20243-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="20243-128">2</span><span class="sxs-lookup"><span data-stu-id="20243-128">2</span></span> | <span data-ttu-id="20243-129">Этот флаг используется для создания прототипов.</span><span class="sxs-lookup"><span data-stu-id="20243-129">This flag is used for prototyping.</span></span> <span data-ttu-id="20243-130">Он не выполняет запрос и вместо этого возвращает объект, который выглядит как типичный объект результата.</span><span class="sxs-lookup"><span data-stu-id="20243-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="20243-131">0x200</span><span class="sxs-lookup"><span data-stu-id="20243-131">0x200</span></span> | <span data-ttu-id="20243-132">Вызывает прямой доступ к поставщику для указанного класса, не обращаясь к его родительскому классу или подклассам.</span><span class="sxs-lookup"><span data-stu-id="20243-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="20243-133">Для наилучшей производительности рекомендуется использовать флаги `WBEM_FLAG_RETURN_IMMEDIATELY`. `WBEM_FLAG_FORWARD_ONLY`</span><span class="sxs-lookup"><span data-stu-id="20243-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="20243-134">окне Как правило, это значение `null`равно.</span><span class="sxs-lookup"><span data-stu-id="20243-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="20243-135">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные классы.</span><span class="sxs-lookup"><span data-stu-id="20243-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="20243-136">заполняет Если ошибка не возникает, получает указатель на перечислитель, позволяющий вызывающему объекту получить экземпляры в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="20243-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="20243-137">Запрос может иметь результирующий набор с нулевым числом экземпляров.</span><span class="sxs-lookup"><span data-stu-id="20243-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="20243-138">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="20243-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="20243-139">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="20243-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="20243-140">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="20243-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="20243-141">окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="20243-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="20243-142">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="20243-142">[in] The user name.</span></span> <span data-ttu-id="20243-143">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="20243-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="20243-144">окне Пароль.</span><span class="sxs-lookup"><span data-stu-id="20243-144">[in] The password.</span></span> <span data-ttu-id="20243-145">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="20243-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="20243-146">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="20243-146">[in] The domain name of the user.</span></span> <span data-ttu-id="20243-147">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="20243-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="20243-148">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="20243-148">Return value</span></span>

<span data-ttu-id="20243-149">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="20243-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="20243-150">Константа</span><span class="sxs-lookup"><span data-stu-id="20243-150">Constant</span></span>  |<span data-ttu-id="20243-151">Значение</span><span class="sxs-lookup"><span data-stu-id="20243-151">Value</span></span>  |<span data-ttu-id="20243-152">Описание</span><span class="sxs-lookup"><span data-stu-id="20243-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="20243-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="20243-153">0x80041003</span></span> | <span data-ttu-id="20243-154">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые может возвращать функция.</span><span class="sxs-lookup"><span data-stu-id="20243-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="20243-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="20243-155">0x80041001</span></span> | <span data-ttu-id="20243-156">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="20243-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="20243-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="20243-157">0x80041008</span></span> | <span data-ttu-id="20243-158">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="20243-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="20243-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="20243-159">0x80041017</span></span> | <span data-ttu-id="20243-160">В запросе возникла синтаксическая ошибка.</span><span class="sxs-lookup"><span data-stu-id="20243-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="20243-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="20243-161">0x80041018</span></span> | <span data-ttu-id="20243-162">Запрошенный язык запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="20243-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="20243-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="20243-163">0x8004106c</span></span> | <span data-ttu-id="20243-164">Запрос слишком сложен.</span><span class="sxs-lookup"><span data-stu-id="20243-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="20243-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="20243-165">0x80041006</span></span> | <span data-ttu-id="20243-166">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="20243-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="20243-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="20243-167">0x80041033</span></span> | <span data-ttu-id="20243-168">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="20243-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="20243-169">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="20243-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="20243-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="20243-170">0x80041015</span></span> | <span data-ttu-id="20243-171">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="20243-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="20243-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="20243-172">0x80041002</span></span> | <span data-ttu-id="20243-173">В запросе указан несуществующий класс.</span><span class="sxs-lookup"><span data-stu-id="20243-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="20243-174">0</span><span class="sxs-lookup"><span data-stu-id="20243-174">0</span></span> | <span data-ttu-id="20243-175">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="20243-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="20243-176">Примечания</span><span class="sxs-lookup"><span data-stu-id="20243-176">Remarks</span></span>

<span data-ttu-id="20243-177">Эта функция заключает вызов метода [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) .</span><span class="sxs-lookup"><span data-stu-id="20243-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="20243-178">Эта функция обрабатывает запрос, указанный в `strQuery` параметре, и создает перечислитель, с помощью которого вызывающий может получить доступ к результатам запроса.</span><span class="sxs-lookup"><span data-stu-id="20243-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="20243-179">Перечислитель является указателем на интерфейс [иенумвбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) ; результаты запроса представляют собой экземпляры объектов класса, доступ к которым можно получить через интерфейс [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="20243-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="20243-180">Существует ряд ограничений на количество `AND` ключевых слов и `OR` , которые могут использоваться в запросах WQL.</span><span class="sxs-lookup"><span data-stu-id="20243-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="20243-181">Большое количество ключевых слов WQL, используемых в сложном запросе, может привести к тому `WBEM_E_QUOTA_VIOLATION` , `HRESULT` что инструментарий WMI возвращает код ошибки (или 0x8004106c) как значение.</span><span class="sxs-lookup"><span data-stu-id="20243-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="20243-182">Ограничение ключевых слов WQL зависит от того, насколько сложным является запрос.</span><span class="sxs-lookup"><span data-stu-id="20243-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="20243-183">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="20243-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="20243-184">Требования</span><span class="sxs-lookup"><span data-stu-id="20243-184">Requirements</span></span>

<span data-ttu-id="20243-185">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20243-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="20243-186">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="20243-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="20243-187">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20243-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="20243-188">См. также</span><span class="sxs-lookup"><span data-stu-id="20243-188">See also</span></span>

- [<span data-ttu-id="20243-189">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="20243-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
