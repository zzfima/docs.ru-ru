---
title: Функция CreateClassEnumWmi (Справочник по неуправляемым API)
description: Функция CreateClassEnumWmi Возвращает перечислитель для всех классов, которые удовлетворяют заданным условиям.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b38e4753105932d2464bf78797a6979aeb0a0aee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527843"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="7f84b-103">Функция CreateClassEnumWmi</span><span class="sxs-lookup"><span data-stu-id="7f84b-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="7f84b-104">Возвращает перечислитель для всех классов, которые удовлетворяют указанным критериям выбора.</span><span class="sxs-lookup"><span data-stu-id="7f84b-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7f84b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f84b-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

## <a name="parameters"></a><span data-ttu-id="7f84b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f84b-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="7f84b-107">[in] В противном случае `null` или пусто, имя класса-родителя; перечислитель возвращает только подклассы этого класса.</span><span class="sxs-lookup"><span data-stu-id="7f84b-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="7f84b-108">Если это `null` либо оставьте пустым и `lFlags` является WBEM_FLAG_SHALLOW, возвращает только верхнего уровня классов (классов без родительского класса).</span><span class="sxs-lookup"><span data-stu-id="7f84b-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="7f84b-109">Если это `null` либо оставьте пустым и `lFlags` является `WBEM_FLAG_DEEP`, возвращаются все классы в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="7f84b-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="7f84b-110">[in] Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="7f84b-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="7f84b-111">Следующие значения определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7f84b-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="7f84b-112">Константа</span><span class="sxs-lookup"><span data-stu-id="7f84b-112">Constant</span></span>  |<span data-ttu-id="7f84b-113">Значение</span><span class="sxs-lookup"><span data-stu-id="7f84b-113">Value</span></span>  |<span data-ttu-id="7f84b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7f84b-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="7f84b-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="7f84b-115">0x20000</span></span> | <span data-ttu-id="7f84b-116">Если набор, функция извлекает измененные квалификаторы, хранящиеся в локализованных имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="7f84b-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="7f84b-117">В противном случае набор, функция получает только квалификаторы, хранящихся в пространство имен немедленно.</span><span class="sxs-lookup"><span data-stu-id="7f84b-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="7f84b-118">0</span><span class="sxs-lookup"><span data-stu-id="7f84b-118">0</span></span> | <span data-ttu-id="7f84b-119">Перечисление включает всех подклассов в иерархии, но не для этого класса.</span><span class="sxs-lookup"><span data-stu-id="7f84b-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="7f84b-120">1</span><span class="sxs-lookup"><span data-stu-id="7f84b-120">1</span></span> | <span data-ttu-id="7f84b-121">Перечисление содержит только чистые экземпляры этого класса и исключает все экземпляры из подклассов, которые предоставляют свойства, не найден в этом классе.</span><span class="sxs-lookup"><span data-stu-id="7f84b-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="7f84b-122">0x10</span><span class="sxs-lookup"><span data-stu-id="7f84b-122">0x10</span></span> | <span data-ttu-id="7f84b-123">Этот флаг приводит к Полусинхронный вызов.</span><span class="sxs-lookup"><span data-stu-id="7f84b-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="7f84b-124">0x20</span><span class="sxs-lookup"><span data-stu-id="7f84b-124">0x20</span></span> | <span data-ttu-id="7f84b-125">Функция возвращает только вперед перечислителя.</span><span class="sxs-lookup"><span data-stu-id="7f84b-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="7f84b-126">Обычно перечислители только вперед, выполняются быстрее и использовать меньше памяти, чем обычные перечислители, но они не допускают вызовы [клона](clone.md).</span><span class="sxs-lookup"><span data-stu-id="7f84b-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="7f84b-127">0</span><span class="sxs-lookup"><span data-stu-id="7f84b-127">0</span></span> | <span data-ttu-id="7f84b-128">WMI сохраняет указатели на объекты в enumration до их появления.</span><span class="sxs-lookup"><span data-stu-id="7f84b-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="7f84b-129">Рекомендуемые флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY` для достижения оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="7f84b-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="7f84b-130">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="7f84b-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="7f84b-131">В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы.</span><span class="sxs-lookup"><span data-stu-id="7f84b-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="7f84b-132">[out] Получает указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="7f84b-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="7f84b-133">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="7f84b-133">[in] The authorization level.</span></span>

<span data-ttu-id="7f84b-134">`impLevel` [in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="7f84b-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="7f84b-135">[in] Указатель на [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объект, представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="7f84b-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="7f84b-136">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="7f84b-136">[in] The user name.</span></span> <span data-ttu-id="7f84b-137">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="7f84b-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="7f84b-138">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="7f84b-138">[in] The password.</span></span> <span data-ttu-id="7f84b-139">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="7f84b-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="7f84b-140">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="7f84b-140">[in] The domain name of the user.</span></span> <span data-ttu-id="7f84b-141">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="7f84b-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="7f84b-142">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7f84b-142">Return value</span></span>

<span data-ttu-id="7f84b-143">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7f84b-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7f84b-144">Константа</span><span class="sxs-lookup"><span data-stu-id="7f84b-144">Constant</span></span>  |<span data-ttu-id="7f84b-145">Значение</span><span class="sxs-lookup"><span data-stu-id="7f84b-145">Value</span></span>  |<span data-ttu-id="7f84b-146">Описание</span><span class="sxs-lookup"><span data-stu-id="7f84b-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="7f84b-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="7f84b-147">0x80041003</span></span> | <span data-ttu-id="7f84b-148">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые функция может вернуть.</span><span class="sxs-lookup"><span data-stu-id="7f84b-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="7f84b-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7f84b-149">0x80041001</span></span> | <span data-ttu-id="7f84b-150">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7f84b-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="7f84b-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="7f84b-151">0x80041010</span></span> | <span data-ttu-id="7f84b-152">`strSuperClass` — не существует.</span><span class="sxs-lookup"><span data-stu-id="7f84b-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7f84b-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7f84b-153">0x80041008</span></span> | <span data-ttu-id="7f84b-154">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="7f84b-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7f84b-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7f84b-155">0x80041006</span></span> | <span data-ttu-id="7f84b-156">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="7f84b-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="7f84b-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="7f84b-157">0x80041033</span></span> | <span data-ttu-id="7f84b-158">WMI был, вероятно, остановлена или перезапустить.</span><span class="sxs-lookup"><span data-stu-id="7f84b-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="7f84b-159">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="7f84b-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="7f84b-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="7f84b-160">0x80041015</span></span> | <span data-ttu-id="7f84b-161">Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="7f84b-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7f84b-162">0</span><span class="sxs-lookup"><span data-stu-id="7f84b-162">0</span></span> | <span data-ttu-id="7f84b-163">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="7f84b-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7f84b-164">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f84b-164">Remarks</span></span>

<span data-ttu-id="7f84b-165">Эта функция создает оболочку для вызова [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) метод.</span><span class="sxs-lookup"><span data-stu-id="7f84b-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="7f84b-166">Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="7f84b-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f84b-167">Требования</span><span class="sxs-lookup"><span data-stu-id="7f84b-167">Requirements</span></span>  
 <span data-ttu-id="7f84b-168">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f84b-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f84b-169">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7f84b-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7f84b-170">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7f84b-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f84b-171">См. также</span><span class="sxs-lookup"><span data-stu-id="7f84b-171">See also</span></span>  
[<span data-ttu-id="7f84b-172">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7f84b-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
