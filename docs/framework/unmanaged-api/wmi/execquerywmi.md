---
title: Функция ExecQueryWmi (Справочник по неуправляемым API)
description: Функция ExecQueryWmi выполняет запрос для получения объектов.
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
ms.openlocfilehash: b482f2ca2e2d5c06e69945adb71aa6c0f5d26465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="execquerywmi-function"></a><span data-ttu-id="8f20e-103">Функция ExecQueryWmi</span><span class="sxs-lookup"><span data-stu-id="8f20e-103">ExecQueryWmi function</span></span>
<span data-ttu-id="8f20e-104">Выполняет запрос для получения объектов.</span><span class="sxs-lookup"><span data-stu-id="8f20e-104">Executes a query to retrieve objects.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8f20e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f20e-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="8f20e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f20e-106">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="8f20e-107">[in] Строка с допустимым запросом язык, поддерживаемый управления Windows.</span><span class="sxs-lookup"><span data-stu-id="8f20e-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="8f20e-108">Он должен быть «WQL», сокращение для языка запросов WMI.</span><span class="sxs-lookup"><span data-stu-id="8f20e-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="8f20e-109">[in] Текст запроса.</span><span class="sxs-lookup"><span data-stu-id="8f20e-109">[in] The text of the query.</span></span> <span data-ttu-id="8f20e-110">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="8f20e-110">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="8f20e-111">[in] Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="8f20e-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="8f20e-112">Следующие значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8f20e-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

| <span data-ttu-id="8f20e-113">Константа</span><span class="sxs-lookup"><span data-stu-id="8f20e-113">Constant</span></span> | <span data-ttu-id="8f20e-114">Значение</span><span class="sxs-lookup"><span data-stu-id="8f20e-114">Value</span></span>  | <span data-ttu-id="8f20e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8f20e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="8f20e-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="8f20e-116">0x20000</span></span> | <span data-ttu-id="8f20e-117">Если набор, функция возвращает изменяемые квалификаторы, хранимых в локализованных имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="8f20e-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="8f20e-118">В противном случае набор, функция возвращает только квалификаторы, хранимых в интерпретации имен.</span><span class="sxs-lookup"><span data-stu-id="8f20e-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="8f20e-119">0x10</span><span class="sxs-lookup"><span data-stu-id="8f20e-119">0x10</span></span> | <span data-ttu-id="8f20e-120">Флаг вызывает полусинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="8f20e-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="8f20e-121">0x20</span><span class="sxs-lookup"><span data-stu-id="8f20e-121">0x20</span></span> | <span data-ttu-id="8f20e-122">Эта функция возвращает только вперед перечислителя.</span><span class="sxs-lookup"><span data-stu-id="8f20e-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="8f20e-123">Обычно последовательным перечислители работают быстрее и использовать меньше памяти, чем обычный перечислители, но не разрешать вызовы [клон](clone.md).</span><span class="sxs-lookup"><span data-stu-id="8f20e-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="8f20e-124">0</span><span class="sxs-lookup"><span data-stu-id="8f20e-124">0</span></span> | <span data-ttu-id="8f20e-125">WMI сохраняет указатели на объекты в enumration до их появления.</span><span class="sxs-lookup"><span data-stu-id="8f20e-125">WMI retains pointers to objects in the enumration until they are released.</span></span> | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="8f20e-126">0x100</span><span class="sxs-lookup"><span data-stu-id="8f20e-126">0x100</span></span> | <span data-ttu-id="8f20e-127">Обеспечивает все возвращаемые объекты имели достаточно сведений в них так, системные свойства, такие как **__PATH**, **__RELPATH**, и **__SERVER**, не являются `null`.</span><span class="sxs-lookup"><span data-stu-id="8f20e-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="8f20e-128">2</span><span class="sxs-lookup"><span data-stu-id="8f20e-128">2</span></span> | <span data-ttu-id="8f20e-129">Этот флаг используется для создания прототипов.</span><span class="sxs-lookup"><span data-stu-id="8f20e-129">This flag is used for prototyping.</span></span> <span data-ttu-id="8f20e-130">Он не выполняет запрос и возвращает объект, который выглядит как типичный результирующий объект.</span><span class="sxs-lookup"><span data-stu-id="8f20e-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="8f20e-131">0x200</span><span class="sxs-lookup"><span data-stu-id="8f20e-131">0x200</span></span> | <span data-ttu-id="8f20e-132">Причины прямой доступ к поставщику для класса, указанного независимо от его родительского класса и его подклассов.</span><span class="sxs-lookup"><span data-stu-id="8f20e-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="8f20e-133">Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="8f20e-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="8f20e-134">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="8f20e-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="8f20e-135">В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы.</span><span class="sxs-lookup"><span data-stu-id="8f20e-135">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="8f20e-136">[out] Если ошибок нет, получающей указатель на перечислитель, который позволяет вызывающему объекту получить экземпляры в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="8f20e-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="8f20e-137">Запрос может содержать результирующий набор с нуля экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8f20e-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="8f20e-138">В разделе [примечания](#remarks) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="8f20e-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="8f20e-139">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="8f20e-139">[in] The authorization level.</span></span>

<span data-ttu-id="8f20e-140">`impLevel` [in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="8f20e-140">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="8f20e-141">[in] Указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) , представляющий текущего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8f20e-141">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="8f20e-142">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f20e-142">[in] The user name.</span></span> <span data-ttu-id="8f20e-143">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="8f20e-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="8f20e-144">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="8f20e-144">[in] The password.</span></span> <span data-ttu-id="8f20e-145">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="8f20e-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="8f20e-146">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f20e-146">[in] The domain name of the user.</span></span> <span data-ttu-id="8f20e-147">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="8f20e-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="8f20e-148">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f20e-148">Return value</span></span>

<span data-ttu-id="8f20e-149">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8f20e-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8f20e-150">Константа</span><span class="sxs-lookup"><span data-stu-id="8f20e-150">Constant</span></span>  |<span data-ttu-id="8f20e-151">Значение</span><span class="sxs-lookup"><span data-stu-id="8f20e-151">Value</span></span>  |<span data-ttu-id="8f20e-152">Описание</span><span class="sxs-lookup"><span data-stu-id="8f20e-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="8f20e-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="8f20e-153">0x80041003</span></span> | <span data-ttu-id="8f20e-154">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть.</span><span class="sxs-lookup"><span data-stu-id="8f20e-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="8f20e-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8f20e-155">0x80041001</span></span> | <span data-ttu-id="8f20e-156">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="8f20e-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8f20e-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8f20e-157">0x80041008</span></span> | <span data-ttu-id="8f20e-158">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="8f20e-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="8f20e-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="8f20e-159">0x80041017</span></span> | <span data-ttu-id="8f20e-160">Запрос содержит синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="8f20e-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="8f20e-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="8f20e-161">0x80041018</span></span> | <span data-ttu-id="8f20e-162">Запрошенный язык запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8f20e-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="8f20e-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="8f20e-163">0x8004106c</span></span> | <span data-ttu-id="8f20e-164">Запрос слишком сложен.</span><span class="sxs-lookup"><span data-stu-id="8f20e-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8f20e-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8f20e-165">0x80041006</span></span> | <span data-ttu-id="8f20e-166">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="8f20e-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="8f20e-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="8f20e-167">0x80041033</span></span> | <span data-ttu-id="8f20e-168">WMI был, скорее всего, остановлен и перезапускать.</span><span class="sxs-lookup"><span data-stu-id="8f20e-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="8f20e-169">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="8f20e-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="8f20e-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="8f20e-170">0x80041015</span></span> | <span data-ttu-id="8f20e-171">Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="8f20e-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="8f20e-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8f20e-172">0x80041002</span></span> | <span data-ttu-id="8f20e-173">Запрос указывает класс, который не существует.</span><span class="sxs-lookup"><span data-stu-id="8f20e-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8f20e-174">0</span><span class="sxs-lookup"><span data-stu-id="8f20e-174">0</span></span> | <span data-ttu-id="8f20e-175">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="8f20e-175">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8f20e-176">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f20e-176">Remarks</span></span>

<span data-ttu-id="8f20e-177">Эта функция создает оболочку для вызова [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="8f20e-177">This function wraps a call to the [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="8f20e-178">Эта функция обрабатывает запрос, указанный в `strQuery` параметр и создает перечислитель, через который вызывающий объект может получить доступ к результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="8f20e-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="8f20e-179">Перечислитель является указателем на [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) интерфейса; запроса результаты являются экземплярами класса объектов, доступны через [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f20e-179">The enumerator is a pointer to an [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interface; the query results are instances of class objects made available through the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interface.</span></span>

<span data-ttu-id="8f20e-180">Существуют ограничения на число `AND` и `OR` ключевые слова, которые могут использоваться в запросах WQL.</span><span class="sxs-lookup"><span data-stu-id="8f20e-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="8f20e-181">Большое число WQL ключевые слова, используемые в сложных запросах может привести к WMI для возвращения `WBEM_E_QUOTA_VIOLATION` (или 0x8004106c) код ошибки, что `HRESULT` значение.</span><span class="sxs-lookup"><span data-stu-id="8f20e-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="8f20e-182">Предельного количества ключевых слов языка WQL зависит от сложности запроса.</span><span class="sxs-lookup"><span data-stu-id="8f20e-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="8f20e-183">При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="8f20e-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f20e-184">Требования</span><span class="sxs-lookup"><span data-stu-id="8f20e-184">Requirements</span></span>  
 <span data-ttu-id="8f20e-185">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f20e-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f20e-186">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8f20e-186">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8f20e-187">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8f20e-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f20e-188">См. также</span><span class="sxs-lookup"><span data-stu-id="8f20e-188">See also</span></span>  
[<span data-ttu-id="8f20e-189">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="8f20e-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
