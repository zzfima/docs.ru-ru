---
title: "Функция CreateInstanceEnumWmi (Справочник по неуправляемым API)"
description: "Функция CreateInstanceEnumWmi Возвращает перечислитель, содержащий экземпляры указанного класса, соответствующие условиям выбора."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateInstanceEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateInstanceEnumWmi
helpviewer_keywords: CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19a4102796da7a5692eb5b9b459a6a95ff7409f9
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="580c9-103">Функция CreateInstanceEnumWmi</span><span class="sxs-lookup"><span data-stu-id="580c9-103">CreateInstanceEnumWmi function</span></span>
<span data-ttu-id="580c9-104">Возвращает перечислитель, который возвращает экземпляры указанного класса, удовлетворяющих указанные критерии выбора.</span><span class="sxs-lookup"><span data-stu-id="580c9-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="580c9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="580c9-105">Syntax</span></span>  
  
```  
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
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

## <a name="parameters"></a><span data-ttu-id="580c9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="580c9-106">Parameters</span></span>

`strFilter`    
<span data-ttu-id="580c9-107">[in] Имя класса, для которого требуются экземпляров.</span><span class="sxs-lookup"><span data-stu-id="580c9-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="580c9-108">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="580c9-108">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="580c9-109">[in] Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="580c9-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="580c9-110">Следующие значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="580c9-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="580c9-111">Константа</span><span class="sxs-lookup"><span data-stu-id="580c9-111">Constant</span></span>  |<span data-ttu-id="580c9-112">Значение</span><span class="sxs-lookup"><span data-stu-id="580c9-112">Value</span></span>  |<span data-ttu-id="580c9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="580c9-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="580c9-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="580c9-114">0x20000</span></span> | <span data-ttu-id="580c9-115">Если набор, функция возвращает изменяемые квалификаторы, хранимых в локализованных имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="580c9-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="580c9-116">В противном случае набор, функция возвращает только квалификаторы, хранимых в интерпретации имен.</span><span class="sxs-lookup"><span data-stu-id="580c9-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="580c9-117">0</span><span class="sxs-lookup"><span data-stu-id="580c9-117">0</span></span> | <span data-ttu-id="580c9-118">Перечисление включает это и всех подклассов в иерархии.</span><span class="sxs-lookup"><span data-stu-id="580c9-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="580c9-119">1</span><span class="sxs-lookup"><span data-stu-id="580c9-119">1</span></span> | <span data-ttu-id="580c9-120">Перечисление содержит только чистые экземпляры этого класса и исключает все экземпляры подклассов, которые предоставляют свойства, не найденные в этом классе.</span><span class="sxs-lookup"><span data-stu-id="580c9-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="580c9-121">0x10</span><span class="sxs-lookup"><span data-stu-id="580c9-121">0x10</span></span> | <span data-ttu-id="580c9-122">Флаг вызывает полусинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="580c9-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="580c9-123">0x20</span><span class="sxs-lookup"><span data-stu-id="580c9-123">0x20</span></span> | <span data-ttu-id="580c9-124">Эта функция возвращает только вперед перечислителя.</span><span class="sxs-lookup"><span data-stu-id="580c9-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="580c9-125">Обычно последовательным перечислители работают быстрее и использовать меньше памяти, чем обычный перечислители, но не разрешать вызовы [клон](clone.md).</span><span class="sxs-lookup"><span data-stu-id="580c9-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="580c9-126">0</span><span class="sxs-lookup"><span data-stu-id="580c9-126">0</span></span> | <span data-ttu-id="580c9-127">WMI сохраняет указатели на объекты в enumration до их появления.</span><span class="sxs-lookup"><span data-stu-id="580c9-127">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="580c9-128">Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="580c9-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="580c9-129">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="580c9-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="580c9-130">В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="580c9-130">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`  
<span data-ttu-id="580c9-131">[out] Получает указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="580c9-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="580c9-132">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="580c9-132">[in] The authorization level.</span></span>

<span data-ttu-id="580c9-133">`impLevel`[in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="580c9-133">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="580c9-134">[in] Указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) , представляющий текущего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="580c9-134">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="580c9-135">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="580c9-135">[in] The user name.</span></span> <span data-ttu-id="580c9-136">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="580c9-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="580c9-137">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="580c9-137">[in] The password.</span></span> <span data-ttu-id="580c9-138">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="580c9-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="580c9-139">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="580c9-139">[in] The domain name of the user.</span></span> <span data-ttu-id="580c9-140">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="580c9-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="580c9-141">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="580c9-141">Return value</span></span>

<span data-ttu-id="580c9-142">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="580c9-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="580c9-143">Константа</span><span class="sxs-lookup"><span data-stu-id="580c9-143">Constant</span></span>  |<span data-ttu-id="580c9-144">Значение</span><span class="sxs-lookup"><span data-stu-id="580c9-144">Value</span></span>  |<span data-ttu-id="580c9-145">Описание</span><span class="sxs-lookup"><span data-stu-id="580c9-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="580c9-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="580c9-146">0x80041003</span></span> | <span data-ttu-id="580c9-147">Пользователь не имеет разрешения на просмотр экземпляров указанного класса.</span><span class="sxs-lookup"><span data-stu-id="580c9-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="580c9-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="580c9-148">0x80041001</span></span> | <span data-ttu-id="580c9-149">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="580c9-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="580c9-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="580c9-150">0x80041010</span></span> | <span data-ttu-id="580c9-151">`strFilter` — не существует.</span><span class="sxs-lookup"><span data-stu-id="580c9-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="580c9-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="580c9-152">0x80041008</span></span> | <span data-ttu-id="580c9-153">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="580c9-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="580c9-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="580c9-154">0x80041006</span></span> | <span data-ttu-id="580c9-155">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="580c9-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="580c9-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="580c9-156">0x80041033</span></span> | <span data-ttu-id="580c9-157">WMI был, скорее всего, остановлен и перезапускать.</span><span class="sxs-lookup"><span data-stu-id="580c9-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="580c9-158">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="580c9-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="580c9-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="580c9-159">0x80041015</span></span> | <span data-ttu-id="580c9-160">Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="580c9-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="580c9-161">0</span><span class="sxs-lookup"><span data-stu-id="580c9-161">0</span></span> | <span data-ttu-id="580c9-162">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="580c9-162">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="580c9-163">Примечания</span><span class="sxs-lookup"><span data-stu-id="580c9-163">Remarks</span></span>

<span data-ttu-id="580c9-164">Эта функция создает оболочку для вызова [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="580c9-164">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="580c9-165">Обратите внимание, что возвращаемый перечислитель может иметь ноль элементов.</span><span class="sxs-lookup"><span data-stu-id="580c9-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="580c9-166">При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="580c9-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="580c9-167">Требования</span><span class="sxs-lookup"><span data-stu-id="580c9-167">Requirements</span></span>  
 <span data-ttu-id="580c9-168">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="580c9-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="580c9-169">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="580c9-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="580c9-170">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="580c9-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580c9-171">См. также</span><span class="sxs-lookup"><span data-stu-id="580c9-171">See also</span></span>  
[<span data-ttu-id="580c9-172">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="580c9-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
