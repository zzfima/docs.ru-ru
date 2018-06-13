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
ms.openlocfilehash: 4b5c26ab9c273b134915eea39078a83f569bcd32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462420"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="9150c-103">Функция ExecNotificationQueryWmi</span><span class="sxs-lookup"><span data-stu-id="9150c-103">ExecNotificationQueryWmi function</span></span>
<span data-ttu-id="9150c-104">Выполняет запрос для получения событий.</span><span class="sxs-lookup"><span data-stu-id="9150c-104">Executes a query to receive events.</span></span> <span data-ttu-id="9150c-105">Вызов возвращается немедленно, а вызывающий объект может выполнять опрос возвращаемый перечислитель для событий по мере их поступления.</span><span class="sxs-lookup"><span data-stu-id="9150c-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="9150c-106">Освобождение возвращаемый перечислитель отменяет запрос.</span><span class="sxs-lookup"><span data-stu-id="9150c-106">Releasing the returned enumerator cancels the query.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9150c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9150c-107">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="9150c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="9150c-108">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="9150c-109">[in] Строка с допустимым запросом язык, поддерживаемый управления Windows.</span><span class="sxs-lookup"><span data-stu-id="9150c-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="9150c-110">Он должен быть «WQL», сокращение для языка запросов WMI.</span><span class="sxs-lookup"><span data-stu-id="9150c-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="9150c-111">[in] Текст запроса.</span><span class="sxs-lookup"><span data-stu-id="9150c-111">[in] The text of the query.</span></span> <span data-ttu-id="9150c-112">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="9150c-112">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="9150c-113">[in] Комбинация из двух следующих флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="9150c-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="9150c-114">Эти значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="9150c-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> 

| <span data-ttu-id="9150c-115">Константа</span><span class="sxs-lookup"><span data-stu-id="9150c-115">Constant</span></span> | <span data-ttu-id="9150c-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9150c-116">Value</span></span>  | <span data-ttu-id="9150c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9150c-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="9150c-118">0x10</span><span class="sxs-lookup"><span data-stu-id="9150c-118">0x10</span></span> | <span data-ttu-id="9150c-119">Флаг вызывает полусинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="9150c-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="9150c-120">Если этот флаг не установлен, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="9150c-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="9150c-121">Это так, как будут получены события постоянно, это означает, что пользователь должен опросить возвращаемый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="9150c-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="9150c-122">Блокирует этот вызов бесконечно делает это невозможно.</span><span class="sxs-lookup"><span data-stu-id="9150c-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="9150c-123">0x20</span><span class="sxs-lookup"><span data-stu-id="9150c-123">0x20</span></span> | <span data-ttu-id="9150c-124">Эта функция возвращает только вперед перечислителя.</span><span class="sxs-lookup"><span data-stu-id="9150c-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="9150c-125">Обычно последовательным перечислители работают быстрее и использовать меньше памяти, чем обычный перечислители, но не разрешать вызовы [клон](clone.md).</span><span class="sxs-lookup"><span data-stu-id="9150c-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`  
<span data-ttu-id="9150c-126">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="9150c-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="9150c-127">В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенные события.</span><span class="sxs-lookup"><span data-stu-id="9150c-127">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested events.</span></span> 

`ppEnum`  
<span data-ttu-id="9150c-128">[out] Если ошибок нет, получающей указатель на перечислитель, который позволяет вызывающему объекту получить экземпляры в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="9150c-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="9150c-129">В разделе [примечания](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="9150c-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="9150c-130">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="9150c-130">[in] The authorization level.</span></span>

<span data-ttu-id="9150c-131">`impLevel` [in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="9150c-131">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="9150c-132">[in] Указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) , представляющий текущего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9150c-132">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="9150c-133">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="9150c-133">[in] The user name.</span></span> <span data-ttu-id="9150c-134">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="9150c-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="9150c-135">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="9150c-135">[in] The password.</span></span> <span data-ttu-id="9150c-136">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="9150c-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="9150c-137">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="9150c-137">[in] The domain name of the user.</span></span> <span data-ttu-id="9150c-138">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="9150c-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="9150c-139">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9150c-139">Return value</span></span>

<span data-ttu-id="9150c-140">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="9150c-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9150c-141">Константа</span><span class="sxs-lookup"><span data-stu-id="9150c-141">Constant</span></span>  |<span data-ttu-id="9150c-142">Значение</span><span class="sxs-lookup"><span data-stu-id="9150c-142">Value</span></span>  |<span data-ttu-id="9150c-143">Описание</span><span class="sxs-lookup"><span data-stu-id="9150c-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="9150c-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="9150c-144">0x80041003</span></span> | <span data-ttu-id="9150c-145">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть.</span><span class="sxs-lookup"><span data-stu-id="9150c-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="9150c-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="9150c-146">0x80041001</span></span> | <span data-ttu-id="9150c-147">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9150c-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9150c-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9150c-148">0x80041008</span></span> | <span data-ttu-id="9150c-149">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="9150c-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="9150c-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="9150c-150">0x80041010</span></span> | <span data-ttu-id="9150c-151">Запрос указывает класс, который не существует.</span><span class="sxs-lookup"><span data-stu-id="9150c-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="9150c-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="9150c-152">0x80042002</span></span> | <span data-ttu-id="9150c-153">Запрошено слишком много точности в доставки событий.</span><span class="sxs-lookup"><span data-stu-id="9150c-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="9150c-154">Должно быть указано больше погрешность опроса.</span><span class="sxs-lookup"><span data-stu-id="9150c-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="9150c-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="9150c-155">0x80042001</span></span> | <span data-ttu-id="9150c-156">Requess запрос может предоставить больше сведений, чем управления Windows.</span><span class="sxs-lookup"><span data-stu-id="9150c-156">The query requess more information than Windows Management can provide.</span></span> <span data-ttu-id="9150c-157">Это `HRESULT` возвращается, когда запрос приводит к запросу опроса всех объектов в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="9150c-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="9150c-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="9150c-158">0x80041017</span></span> | <span data-ttu-id="9150c-159">Запрос содержит синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="9150c-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="9150c-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="9150c-160">0x80041018</span></span> | <span data-ttu-id="9150c-161">Запрошенный язык запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9150c-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="9150c-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="9150c-162">0x8004106c</span></span> | <span data-ttu-id="9150c-163">Запрос слишком сложен.</span><span class="sxs-lookup"><span data-stu-id="9150c-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9150c-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9150c-164">0x80041006</span></span> | <span data-ttu-id="9150c-165">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="9150c-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="9150c-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="9150c-166">0x80041033</span></span> | <span data-ttu-id="9150c-167">WMI был, скорее всего, остановлен и перезапускать.</span><span class="sxs-lookup"><span data-stu-id="9150c-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="9150c-168">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="9150c-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="9150c-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="9150c-169">0x80041015</span></span> | <span data-ttu-id="9150c-170">Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="9150c-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="9150c-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="9150c-171">0x80041058</span></span> | <span data-ttu-id="9150c-172">Не удается обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="9150c-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9150c-173">0</span><span class="sxs-lookup"><span data-stu-id="9150c-173">0</span></span> | <span data-ttu-id="9150c-174">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="9150c-174">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9150c-175">Примечания</span><span class="sxs-lookup"><span data-stu-id="9150c-175">Remarks</span></span>

<span data-ttu-id="9150c-176">Эта функция создает оболочку для вызова [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="9150c-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="9150c-177">После возврата функции, вызывающий объект периодически передает возвращаемый `ppEnum` объект [Далее](next.md) функции, если доступны все события.</span><span class="sxs-lookup"><span data-stu-id="9150c-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="9150c-178">Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL.</span><span class="sxs-lookup"><span data-stu-id="9150c-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="9150c-179">Большое число WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки, что `HRESULT` значение.</span><span class="sxs-lookup"><span data-stu-id="9150c-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="9150c-180">Предельного количества ключевых слов языка WQL зависит от сложности запроса.</span><span class="sxs-lookup"><span data-stu-id="9150c-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="9150c-181">При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="9150c-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="9150c-182">Требования</span><span class="sxs-lookup"><span data-stu-id="9150c-182">Requirements</span></span>  
 <span data-ttu-id="9150c-183">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9150c-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9150c-184">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9150c-184">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9150c-185">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9150c-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9150c-186">См. также</span><span class="sxs-lookup"><span data-stu-id="9150c-186">See also</span></span>  
[<span data-ttu-id="9150c-187">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="9150c-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
