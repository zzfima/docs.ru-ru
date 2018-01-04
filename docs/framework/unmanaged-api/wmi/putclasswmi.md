---
title: "Функция PutClassWmi (Справочник по неуправляемым API)"
description: "Функция PutClassWmi создает новый класс, или обновляет существующую."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutClassWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutClassWmi
helpviewer_keywords: PutClassWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 219cec2096cd3d1dfe1e0d3c0903b62692e444e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="putclasswmi-function"></a><span data-ttu-id="1416b-103">Функция PutClassWmi</span><span class="sxs-lookup"><span data-stu-id="1416b-103">PutClassWmi function</span></span>
<span data-ttu-id="1416b-104">Создает новый класс, или обновляет существующую.</span><span class="sxs-lookup"><span data-stu-id="1416b-104">Creates a new class or updates an existing one.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1416b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1416b-105">Syntax</span></span>  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="1416b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1416b-106">Parameters</span></span>

`pObject`    
<span data-ttu-id="1416b-107">[in] Указатель является допустимым определением класса.</span><span class="sxs-lookup"><span data-stu-id="1416b-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="1416b-108">Необходимо правильно инициализировать со всеми значениями обязательное свойство.</span><span class="sxs-lookup"><span data-stu-id="1416b-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`   
<span data-ttu-id="1416b-109">[in] Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="1416b-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="1416b-110">Следующие значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1416b-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="1416b-111">Константа</span><span class="sxs-lookup"><span data-stu-id="1416b-111">Constant</span></span>  |<span data-ttu-id="1416b-112">Значение</span><span class="sxs-lookup"><span data-stu-id="1416b-112">Value</span></span>  |<span data-ttu-id="1416b-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="1416b-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="1416b-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="1416b-114">0x20000</span></span> | <span data-ttu-id="1416b-115">Если набор WMI не сохраняет любые квалификаторы с измененные версии.</span><span class="sxs-lookup"><span data-stu-id="1416b-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> </br> <span data-ttu-id="1416b-116">В противном случае набор, предполагается этот объект не локализован, что все квалификаторы — storedwith данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1416b-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="1416b-117">0</span><span class="sxs-lookup"><span data-stu-id="1416b-117">0</span></span> | <span data-ttu-id="1416b-118">Создайте класс, если она не существует, или перезаписать его, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="1416b-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="1416b-119">1</span><span class="sxs-lookup"><span data-stu-id="1416b-119">1</span></span> | <span data-ttu-id="1416b-120">Обновите класс.</span><span class="sxs-lookup"><span data-stu-id="1416b-120">Update the class.</span></span> <span data-ttu-id="1416b-121">Класс должен существовать для успешного вызова.</span><span class="sxs-lookup"><span data-stu-id="1416b-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="1416b-122">2</span><span class="sxs-lookup"><span data-stu-id="1416b-122">2</span></span> | <span data-ttu-id="1416b-123">Создание класса.</span><span class="sxs-lookup"><span data-stu-id="1416b-123">Create the class.</span></span> <span data-ttu-id="1416b-124">Вызов завершается неудачей, если класс уже существует.</span><span class="sxs-lookup"><span data-stu-id="1416b-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="1416b-125">0x10</span><span class="sxs-lookup"><span data-stu-id="1416b-125">0x10</span></span> | <span data-ttu-id="1416b-126">Флаг вызывает полусинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="1416b-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="1416b-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="1416b-127">0x10000</span></span> | <span data-ttu-id="1416b-128">Принудительная поставщики должны указывать этот флаг, при вызове `PutClassWmi` для указания, что этот класс был изменен.</span><span class="sxs-lookup"><span data-stu-id="1416b-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="1416b-129">0</span><span class="sxs-lookup"><span data-stu-id="1416b-129">0</span></span> | <span data-ttu-id="1416b-130">Позволяет класс обновляться, если не производные классы и экземпляры этого класса не существует.</span><span class="sxs-lookup"><span data-stu-id="1416b-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="1416b-131">Она также позволяет обновлений во всех случаях, если изменение выполнено лишь в незначительной квалификаторы, например квалификатор описания.</span><span class="sxs-lookup"><span data-stu-id="1416b-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="1416b-132">Если класс имеет экземпляры или изменения относятся к важным квалификаторы, обновление завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1416b-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="1416b-133">0x20</span><span class="sxs-lookup"><span data-stu-id="1416b-133">0x20</span></span> | <span data-ttu-id="1416b-134">Обеспечивает обновление классов даже при наличии дочерних классов, при условии, что изменение не вызовет конфликты с дочерними классами.</span><span class="sxs-lookup"><span data-stu-id="1416b-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="1416b-135">Например этот флаг позволяет новое свойство для добавления базового класса, который не упоминался ранее в любом дочернем классе.</span><span class="sxs-lookup"><span data-stu-id="1416b-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="1416b-136">Если класс имеет экземпляры, обновление не выполнено.</span><span class="sxs-lookup"><span data-stu-id="1416b-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="1416b-137">0x40</span><span class="sxs-lookup"><span data-stu-id="1416b-137">0x40</span></span> | <span data-ttu-id="1416b-138">Вызывает принудительное обновление классов при наличии конфликтующих дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="1416b-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="1416b-139">Например этот флаг принудительное обновление, если квалификатор определена в дочернем классе, и пытается добавить же квалификатор, который конфликтует с существующие один thte базового класса.</span><span class="sxs-lookup"><span data-stu-id="1416b-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with thte existing one.</span></span> <span data-ttu-id="1416b-140">В принудительном режиме tis конфликт разрешается путем удаления квалификатора в дочернем классе.</span><span class="sxs-lookup"><span data-stu-id="1416b-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`  
<span data-ttu-id="1416b-141">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="1416b-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="1416b-142">В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы.</span><span class="sxs-lookup"><span data-stu-id="1416b-142">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="1416b-143">[out] Если `null`, этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="1416b-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="1416b-144">Если `lFlags` содержит `WBEM_FLAG_RETURN_IMMEDIATELY`, функция немедленно возвращает `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="1416b-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="1416b-145">`ppCallResult` Параметр получает указатель на новый [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) объекта.</span><span class="sxs-lookup"><span data-stu-id="1416b-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="1416b-146">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1416b-146">Return value</span></span>

<span data-ttu-id="1416b-147">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1416b-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1416b-148">Константа</span><span class="sxs-lookup"><span data-stu-id="1416b-148">Constant</span></span>  |<span data-ttu-id="1416b-149">Значение</span><span class="sxs-lookup"><span data-stu-id="1416b-149">Value</span></span>  |<span data-ttu-id="1416b-150">Описание:</span><span class="sxs-lookup"><span data-stu-id="1416b-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="1416b-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="1416b-151">0x80041003</span></span> | <span data-ttu-id="1416b-152">Пользователь не имеет разрешения на создание или изменение классы.</span><span class="sxs-lookup"><span data-stu-id="1416b-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="1416b-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1416b-153">0x80041001</span></span> | <span data-ttu-id="1416b-154">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1416b-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="1416b-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="1416b-155">0x80041010</span></span> | <span data-ttu-id="1416b-156">Указанный класс не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="1416b-156">The specified class is not valid.</span></span> <span data-ttu-id="1416b-157">Как правило, это означает, что `pObject` указывает экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="1416b-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1416b-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1416b-158">0x80041008</span></span> | <span data-ttu-id="1416b-159">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="1416b-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="1416b-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="1416b-160">0x80041016</span></span> | <span data-ttu-id="1416b-161">Недопустимое имя указанного класса.</span><span class="sxs-lookup"><span data-stu-id="1416b-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="1416b-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="1416b-162">0x80041025</span></span> | <span data-ttu-id="1416b-163">Попытка сделать изменение, которое аннулирует подкласс.</span><span class="sxs-lookup"><span data-stu-id="1416b-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="1416b-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="1416b-164">0x80041019</span></span> | <span data-ttu-id="1416b-165">`WBEM_FLAG_CREATE_ONLY` Был указан флаг, но класс уже существует.</span><span class="sxs-lookup"><span data-stu-id="1416b-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="1416b-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1416b-166">0x80041002</span></span> | <span data-ttu-id="1416b-167">`WBEM_FLAG_UPDATE_ONLY`был указан в `lFlags`, и этот класс не найден.</span><span class="sxs-lookup"><span data-stu-id="1416b-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="1416b-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="1416b-168">0x80041020</span></span> | <span data-ttu-id="1416b-169">Требуемые свойства для классов, не все заданы.</span><span class="sxs-lookup"><span data-stu-id="1416b-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1416b-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1416b-170">0x80041006</span></span> | <span data-ttu-id="1416b-171">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="1416b-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="1416b-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="1416b-172">0x80041033</span></span> | <span data-ttu-id="1416b-173">WMI был, скорее всего, остановлен и перезапускать.</span><span class="sxs-lookup"><span data-stu-id="1416b-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="1416b-174">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="1416b-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="1416b-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="1416b-175">0x80041015</span></span> | <span data-ttu-id="1416b-176">Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="1416b-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1416b-177">0</span><span class="sxs-lookup"><span data-stu-id="1416b-177">0</span></span> | <span data-ttu-id="1416b-178">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="1416b-178">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1416b-179">Примечания</span><span class="sxs-lookup"><span data-stu-id="1416b-179">Remarks</span></span>

<span data-ttu-id="1416b-180">Эта функция создает оболочку для вызова [IWbemServices::PutClass](https://msdn.microsoft.com/library/aa392113(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="1416b-180">This function wraps a call to the [IWbemServices::PutClass](https://msdn.microsoft.com/library/aa392113(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1416b-181">Пользователь не может создать классы, имена которых начинаться или заканчиваться символом подчеркивания chacater</span><span class="sxs-lookup"><span data-stu-id="1416b-181">The user may not create classes with names that begin or end with an underscore chacater</span></span>

<span data-ttu-id="1416b-182">При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="1416b-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="1416b-183">Требования</span><span class="sxs-lookup"><span data-stu-id="1416b-183">Requirements</span></span>  
 <span data-ttu-id="1416b-184">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1416b-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1416b-185">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1416b-185">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1416b-186">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1416b-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1416b-187">См. также</span><span class="sxs-lookup"><span data-stu-id="1416b-187">See also</span></span>  
[<span data-ttu-id="1416b-188">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1416b-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
