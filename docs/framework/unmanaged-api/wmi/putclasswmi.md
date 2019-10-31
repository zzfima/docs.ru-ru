---
title: Функция Путклассвми (Справочник по неуправляемым API)
description: Функция Путклассвми создает новый класс или обновляет существующий.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101782"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="afd59-103">Функция Путклассвми</span><span class="sxs-lookup"><span data-stu-id="afd59-103">PutClassWmi function</span></span>

<span data-ttu-id="afd59-104">Создает новый класс или обновляет существующий.</span><span class="sxs-lookup"><span data-stu-id="afd59-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="afd59-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afd59-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="afd59-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="afd59-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="afd59-107">окне Указатель на допустимое определение класса.</span><span class="sxs-lookup"><span data-stu-id="afd59-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="afd59-108">Она должна быть правильно инициализирована всеми необходимыми значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="afd59-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="afd59-109">окне Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="afd59-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="afd59-110">Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="afd59-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="afd59-111">Константа</span><span class="sxs-lookup"><span data-stu-id="afd59-111">Constant</span></span>  |<span data-ttu-id="afd59-112">значения</span><span class="sxs-lookup"><span data-stu-id="afd59-112">Value</span></span>  |<span data-ttu-id="afd59-113">Описание</span><span class="sxs-lookup"><span data-stu-id="afd59-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="afd59-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="afd59-114">0x20000</span></span> | <span data-ttu-id="afd59-115">Если задано, Инструментарий WMI не сохраняет никаких квалификаторов с измененной разновидностью.</span><span class="sxs-lookup"><span data-stu-id="afd59-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="afd59-116">Если не задано, предполагается, что этот объект не локализован, а все квалификаторы хранятся в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="afd59-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="afd59-117">0</span><span class="sxs-lookup"><span data-stu-id="afd59-117">0</span></span> | <span data-ttu-id="afd59-118">Создайте класс, если он не существует, или перезапишите его, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="afd59-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="afd59-119">1</span><span class="sxs-lookup"><span data-stu-id="afd59-119">1</span></span> | <span data-ttu-id="afd59-120">Обновите класс.</span><span class="sxs-lookup"><span data-stu-id="afd59-120">Update the class.</span></span> <span data-ttu-id="afd59-121">Для успешного вызова класс должен существовать.</span><span class="sxs-lookup"><span data-stu-id="afd59-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="afd59-122">2</span><span class="sxs-lookup"><span data-stu-id="afd59-122">2</span></span> | <span data-ttu-id="afd59-123">Создайте класс.</span><span class="sxs-lookup"><span data-stu-id="afd59-123">Create the class.</span></span> <span data-ttu-id="afd59-124">Вызов завершается ошибкой, если класс уже существует.</span><span class="sxs-lookup"><span data-stu-id="afd59-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="afd59-125">0x10</span><span class="sxs-lookup"><span data-stu-id="afd59-125">0x10</span></span> | <span data-ttu-id="afd59-126">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="afd59-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="afd59-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="afd59-127">0x10000</span></span> | <span data-ttu-id="afd59-128">Поставщики push-уведомлений должны указывать этот флаг при вызове `PutClassWmi`, чтобы указать, что этот класс изменился.</span><span class="sxs-lookup"><span data-stu-id="afd59-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="afd59-129">0</span><span class="sxs-lookup"><span data-stu-id="afd59-129">0</span></span> | <span data-ttu-id="afd59-130">Позволяет обновлять класс, если нет производных классов и экземпляров этого класса.</span><span class="sxs-lookup"><span data-stu-id="afd59-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="afd59-131">Это также позволяет обновлять во всех случаях, если изменение относится только к неважным квалификаторам, например квалификатору Description.</span><span class="sxs-lookup"><span data-stu-id="afd59-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="afd59-132">Если у класса есть экземпляры или изменения, которые относятся к важным квалификаторам, обновление завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="afd59-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="afd59-133">0x20</span><span class="sxs-lookup"><span data-stu-id="afd59-133">0x20</span></span> | <span data-ttu-id="afd59-134">Позволяет обновлять классы даже при наличии дочерних классов, если изменение не вызывает конфликтов с дочерними классами.</span><span class="sxs-lookup"><span data-stu-id="afd59-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="afd59-135">Например, этот флаг позволяет добавить новое свойство в базовый класс, который ранее не упоминался ни в одном из дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="afd59-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="afd59-136">Если класс имеет экземпляры, обновление завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="afd59-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="afd59-137">0x40</span><span class="sxs-lookup"><span data-stu-id="afd59-137">0x40</span></span> | <span data-ttu-id="afd59-138">принудительно обновляет классы при наличии конфликтующих дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="afd59-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="afd59-139">Например, этот флаг приводит к принудительному обновлению, если квалификатор класса определен в дочернем классе, а базовый класс пытается добавить тот же квалификатор, который конфликтует с существующим.</span><span class="sxs-lookup"><span data-stu-id="afd59-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="afd59-140">В принудительном режиме конфликт TIS разрешается путем удаления конфликтующего квалификатора в дочернем классе.</span><span class="sxs-lookup"><span data-stu-id="afd59-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="afd59-141">окне Как правило, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="afd59-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="afd59-142">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные классы.</span><span class="sxs-lookup"><span data-stu-id="afd59-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="afd59-143">заполняет Если `null`, этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="afd59-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="afd59-144">Если `lFlags` содержит `WBEM_FLAG_RETURN_IMMEDIATELY`, функция немедленно возвращает значение `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="afd59-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="afd59-145">Параметр `ppCallResult` получает указатель на новый объект [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult).</span><span class="sxs-lookup"><span data-stu-id="afd59-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="afd59-146">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="afd59-146">Return value</span></span>

<span data-ttu-id="afd59-147">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="afd59-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="afd59-148">Константа</span><span class="sxs-lookup"><span data-stu-id="afd59-148">Constant</span></span>  |<span data-ttu-id="afd59-149">значения</span><span class="sxs-lookup"><span data-stu-id="afd59-149">Value</span></span>  |<span data-ttu-id="afd59-150">Описание</span><span class="sxs-lookup"><span data-stu-id="afd59-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="afd59-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="afd59-151">0x80041003</span></span> | <span data-ttu-id="afd59-152">У пользователя нет разрешения на создание или изменение классов.</span><span class="sxs-lookup"><span data-stu-id="afd59-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="afd59-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="afd59-153">0x80041001</span></span> | <span data-ttu-id="afd59-154">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="afd59-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="afd59-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="afd59-155">0x80041010</span></span> | <span data-ttu-id="afd59-156">Указан недопустимый класс.</span><span class="sxs-lookup"><span data-stu-id="afd59-156">The specified class is not valid.</span></span> <span data-ttu-id="afd59-157">Как правило, это означает, что `pObject` указывает объект экземпляра.</span><span class="sxs-lookup"><span data-stu-id="afd59-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="afd59-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="afd59-158">0x80041008</span></span> | <span data-ttu-id="afd59-159">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="afd59-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="afd59-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="afd59-160">0x80041016</span></span> | <span data-ttu-id="afd59-161">Указано недопустимое имя класса.</span><span class="sxs-lookup"><span data-stu-id="afd59-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="afd59-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="afd59-162">0x80041025</span></span> | <span data-ttu-id="afd59-163">Предпринята попытка внести изменение, которое сделает подкласс недействительным.</span><span class="sxs-lookup"><span data-stu-id="afd59-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="afd59-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="afd59-164">0x80041019</span></span> | <span data-ttu-id="afd59-165">Указан флаг `WBEM_FLAG_CREATE_ONLY`, но класс уже существует.</span><span class="sxs-lookup"><span data-stu-id="afd59-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="afd59-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="afd59-166">0x80041002</span></span> | <span data-ttu-id="afd59-167">`WBEM_FLAG_UPDATE_ONLY` был указан в `lFlags`, а класс не найден.</span><span class="sxs-lookup"><span data-stu-id="afd59-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="afd59-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="afd59-168">0x80041020</span></span> | <span data-ttu-id="afd59-169">Обязательные свойства для классов не заданы.</span><span class="sxs-lookup"><span data-stu-id="afd59-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="afd59-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="afd59-170">0x80041006</span></span> | <span data-ttu-id="afd59-171">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="afd59-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="afd59-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="afd59-172">0x80041033</span></span> | <span data-ttu-id="afd59-173">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="afd59-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="afd59-174">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="afd59-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="afd59-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="afd59-175">0x80041015</span></span> | <span data-ttu-id="afd59-176">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="afd59-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="afd59-177">0</span><span class="sxs-lookup"><span data-stu-id="afd59-177">0</span></span> | <span data-ttu-id="afd59-178">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="afd59-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="afd59-179">Заметки</span><span class="sxs-lookup"><span data-stu-id="afd59-179">Remarks</span></span>

<span data-ttu-id="afd59-180">Эта функция заключает вызов метода [IWbemServices::P уткласс](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) .</span><span class="sxs-lookup"><span data-stu-id="afd59-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="afd59-181">Пользователь может не создавать классы с именами, начинающимися или заканчивающимися символом подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="afd59-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="afd59-182">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="afd59-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="afd59-183">Требования</span><span class="sxs-lookup"><span data-stu-id="afd59-183">Requirements</span></span>

<span data-ttu-id="afd59-184">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afd59-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="afd59-185">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="afd59-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="afd59-186">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="afd59-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="afd59-187">См. также</span><span class="sxs-lookup"><span data-stu-id="afd59-187">See also</span></span>

- [<span data-ttu-id="afd59-188">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="afd59-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
