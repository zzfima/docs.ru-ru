---
title: Функция PutInstanceWmi (Справочник по неуправляемым API)
description: Функция PutInstanceWmi создает или обновляет экземпляр существующего класса.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0db08ef4938a88ee657e2d65dda70edac09df8ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="31f26-103">Функция PutInstanceWmi</span><span class="sxs-lookup"><span data-stu-id="31f26-103">PutInstanceWmi function</span></span>
<span data-ttu-id="31f26-104">Создает или обновляет экземпляр существующего класса.</span><span class="sxs-lookup"><span data-stu-id="31f26-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="31f26-105">Экземпляр записывается в репозиторий WMI.</span><span class="sxs-lookup"><span data-stu-id="31f26-105">The instance is written to the WMI repository.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="31f26-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31f26-106">Syntax</span></span>  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="31f26-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="31f26-107">Parameters</span></span>

`pInst`    
<span data-ttu-id="31f26-108">[in] Указатель на экземпляр должен иметь writen.</span><span class="sxs-lookup"><span data-stu-id="31f26-108">[in] A pointer to the instance to be writen.</span></span>

`lFlags`   
<span data-ttu-id="31f26-109">[in] Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="31f26-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="31f26-110">Следующие значения определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="31f26-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="31f26-111">Константа</span><span class="sxs-lookup"><span data-stu-id="31f26-111">Constant</span></span>  |<span data-ttu-id="31f26-112">Значение</span><span class="sxs-lookup"><span data-stu-id="31f26-112">Value</span></span>  |<span data-ttu-id="31f26-113">Описание</span><span class="sxs-lookup"><span data-stu-id="31f26-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="31f26-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="31f26-114">0x20000</span></span> | <span data-ttu-id="31f26-115">Если задано, WMI не сохраняет любые квалификаторы с **Amended** flavor.</span><span class="sxs-lookup"><span data-stu-id="31f26-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> </br> <span data-ttu-id="31f26-116">В противном случае набор, предполагается этот объект не локализован, что все квалификаторы — storedwith данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="31f26-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="31f26-117">0</span><span class="sxs-lookup"><span data-stu-id="31f26-117">0</span></span> | <span data-ttu-id="31f26-118">Создайте экземпляр, если она не существует, или перезаписать его, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="31f26-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="31f26-119">1</span><span class="sxs-lookup"><span data-stu-id="31f26-119">1</span></span> | <span data-ttu-id="31f26-120">Обновите экземпляр.</span><span class="sxs-lookup"><span data-stu-id="31f26-120">Update the instance.</span></span> <span data-ttu-id="31f26-121">Экземпляр должен существовать для успешного вызова.</span><span class="sxs-lookup"><span data-stu-id="31f26-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="31f26-122">2</span><span class="sxs-lookup"><span data-stu-id="31f26-122">2</span></span> | <span data-ttu-id="31f26-123">Создайте экземпляр.</span><span class="sxs-lookup"><span data-stu-id="31f26-123">Create the instance.</span></span> <span data-ttu-id="31f26-124">Вызов завершается неудачей, если экземпляр уже существует.</span><span class="sxs-lookup"><span data-stu-id="31f26-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="31f26-125">0x10</span><span class="sxs-lookup"><span data-stu-id="31f26-125">0x10</span></span> | <span data-ttu-id="31f26-126">Флаг вызывает полусинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="31f26-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`  
<span data-ttu-id="31f26-127">[in] Как правило, это значение равно `null`.</span><span class="sxs-lookup"><span data-stu-id="31f26-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="31f26-128">В противном случае он является указателем на [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы.</span><span class="sxs-lookup"><span data-stu-id="31f26-128">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="31f26-129">[out] Если `null`, этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="31f26-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="31f26-130">Если `lFlags` содержит `WBEM_FLAG_RETURN_IMMEDIATELY`, функция немедленно возвращает `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="31f26-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="31f26-131">`ppCallResult` Параметр получает указатель на новый [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) объекта.</span><span class="sxs-lookup"><span data-stu-id="31f26-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="31f26-132">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="31f26-132">Return value</span></span>

<span data-ttu-id="31f26-133">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="31f26-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="31f26-134">Константа</span><span class="sxs-lookup"><span data-stu-id="31f26-134">Constant</span></span>  |<span data-ttu-id="31f26-135">Значение</span><span class="sxs-lookup"><span data-stu-id="31f26-135">Value</span></span>  |<span data-ttu-id="31f26-136">Описание</span><span class="sxs-lookup"><span data-stu-id="31f26-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="31f26-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="31f26-137">0x80041003</span></span> | <span data-ttu-id="31f26-138">Пользователь не имеет разрешения на обновление экземпляра указанного класса.</span><span class="sxs-lookup"><span data-stu-id="31f26-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="31f26-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="31f26-139">0x80041001</span></span> | <span data-ttu-id="31f26-140">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="31f26-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="31f26-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="31f26-141">0x80041010</span></span> | <span data-ttu-id="31f26-142">Указан недопустимый класс, поддерживающий этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="31f26-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="31f26-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="31f26-143">0x80041028</span></span> | <span data-ttu-id="31f26-144">`null` был указан для свойства, которое не может быть `null`, например, помеченного атрибутом **индексированное** или **Not_Null** квалификатор.</span><span class="sxs-lookup"><span data-stu-id="31f26-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="31f26-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="31f26-145">0x8004100f</span></span> | <span data-ttu-id="31f26-146">Указанный экземпляр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="31f26-146">The specified instance is not valid.</span></span> <span data-ttu-id="31f26-147">(Например, вызов метода `PutInstanceWmi` с классом возвращает это значение.)</span><span class="sxs-lookup"><span data-stu-id="31f26-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="31f26-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="31f26-148">0x80041008</span></span> | <span data-ttu-id="31f26-149">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="31f26-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="31f26-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="31f26-150">0x80041019</span></span> | <span data-ttu-id="31f26-151">`WBEM_FLAG_CREATE_ONLY` Был указан флаг, но экземпляр уже существует.</span><span class="sxs-lookup"><span data-stu-id="31f26-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="31f26-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="31f26-152">0x80041002</span></span> | <span data-ttu-id="31f26-153">`WBEM_FLAG_UPDATE_ONLY` был указан в `lFlags`, но экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="31f26-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="31f26-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="31f26-154">0x80041006</span></span> | <span data-ttu-id="31f26-155">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="31f26-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="31f26-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="31f26-156">0x80041033</span></span> | <span data-ttu-id="31f26-157">WMI был, скорее всего, остановлен и перезапускать.</span><span class="sxs-lookup"><span data-stu-id="31f26-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="31f26-158">Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз.</span><span class="sxs-lookup"><span data-stu-id="31f26-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="31f26-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="31f26-159">0x80041015</span></span> | <span data-ttu-id="31f26-160">Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="31f26-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="31f26-161">0</span><span class="sxs-lookup"><span data-stu-id="31f26-161">0</span></span> | <span data-ttu-id="31f26-162">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="31f26-162">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="31f26-163">Примечания</span><span class="sxs-lookup"><span data-stu-id="31f26-163">Remarks</span></span>

<span data-ttu-id="31f26-164">Эта функция создает оболочку для вызова [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="31f26-164">This function wraps a call to the [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="31f26-165">`PutInstanceWmi` Функция поддерживает создание экземпляров и обновление экземпляров только существующих классов.</span><span class="sxs-lookup"><span data-stu-id="31f26-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="31f26-166">В зависимости от того как `pCtx` имеет параметр, будут обновлены некоторые или все свойства экземпляра.</span><span class="sxs-lookup"><span data-stu-id="31f26-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span> 

<span data-ttu-id="31f26-167">Если экземпляр, на который указывает `pInst` принадлежит вызовы всех поставщиков, ответственного за классов, от которых происходит подкласса подкласс управления Windows.</span><span class="sxs-lookup"><span data-stu-id="31f26-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="31f26-168">Все эти поставщики должны успешно завершиться для исходного `PutInstanceWmi` для успешного выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="31f26-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="31f26-169">Сначала вызывается поставщик поддержки верхних класс в иерархии.</span><span class="sxs-lookup"><span data-stu-id="31f26-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="31f26-170">Вызывающий порядок продолжается с подклассом класса переднего плана и переход сверху вниз, пока не достигнет Windows управления поставщика для классов, владельца экземпляра, на который указывает `pInst`.</span><span class="sxs-lookup"><span data-stu-id="31f26-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="31f26-171">Управление Windows не вызывает поставщики для любого дочернего класса экземпляра.</span><span class="sxs-lookup"><span data-stu-id="31f26-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span> 

<span data-ttu-id="31f26-172">Если приложение необходимо обновить экземпляр, который принадлежит к иерархии классов: `pInst` параметр должен указывать экземпляр, содержащий свойства, чтобы изменить.</span><span class="sxs-lookup"><span data-stu-id="31f26-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="31f26-173">То есть, рассмотрите возможность целевой экземпляр, которому принадлежит **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="31f26-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="31f26-174">**ClassB** экземпляра является производным от **ClassA**, и **ClassA** определяет свойство **PropA**.</span><span class="sxs-lookup"><span data-stu-id="31f26-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="31f26-175">Если приложению требуется внести изменение значение **PropA** в **ClassB** экземпляр, он должен задать `pInst` для этого экземпляра, а не экземпляр **ClassA** .</span><span class="sxs-lookup"><span data-stu-id="31f26-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="31f26-176">Вызов `PutInstanceWmi` на экземпляр абстрактного класса не допускается.</span><span class="sxs-lookup"><span data-stu-id="31f26-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="31f26-177">При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="31f26-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="31f26-178">Требования</span><span class="sxs-lookup"><span data-stu-id="31f26-178">Requirements</span></span>  
 <span data-ttu-id="31f26-179">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f26-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f26-180">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="31f26-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="31f26-181">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="31f26-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f26-182">См. также</span><span class="sxs-lookup"><span data-stu-id="31f26-182">See also</span></span>  
[<span data-ttu-id="31f26-183">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="31f26-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
