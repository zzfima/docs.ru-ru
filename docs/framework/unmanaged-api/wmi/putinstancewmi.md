---
title: Функция Путинстанцевми (Справочник по неуправляемым API)
description: Функция Путинстанцевми создает или обновляет экземпляр существующего класса.
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
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798369"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="20b4a-103">Функция Путинстанцевми</span><span class="sxs-lookup"><span data-stu-id="20b4a-103">PutInstanceWmi function</span></span>

<span data-ttu-id="20b4a-104">Создает или обновляет экземпляр существующего класса.</span><span class="sxs-lookup"><span data-stu-id="20b4a-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="20b4a-105">Экземпляр записывается в репозиторий WMI.</span><span class="sxs-lookup"><span data-stu-id="20b4a-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="20b4a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20b4a-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="20b4a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="20b4a-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="20b4a-108">окне Указатель на экземпляр, который необходимо записать.</span><span class="sxs-lookup"><span data-stu-id="20b4a-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="20b4a-109">окне Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="20b4a-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="20b4a-110">Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="20b4a-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="20b4a-111">Константа</span><span class="sxs-lookup"><span data-stu-id="20b4a-111">Constant</span></span>  |<span data-ttu-id="20b4a-112">Значение</span><span class="sxs-lookup"><span data-stu-id="20b4a-112">Value</span></span>  |<span data-ttu-id="20b4a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="20b4a-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="20b4a-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="20b4a-114">0x20000</span></span> | <span data-ttu-id="20b4a-115">Если задано, Инструментарий WMI не сохраняет никаких квалификаторов с **измененной** разновидностью.</span><span class="sxs-lookup"><span data-stu-id="20b4a-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="20b4a-116">Если не задано, предполагается, что этот объект не локализован, а все квалификаторы хранятся в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="20b4a-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="20b4a-117">0</span><span class="sxs-lookup"><span data-stu-id="20b4a-117">0</span></span> | <span data-ttu-id="20b4a-118">Создайте экземпляр, если он не существует, или перезапишите его, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="20b4a-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="20b4a-119">1</span><span class="sxs-lookup"><span data-stu-id="20b4a-119">1</span></span> | <span data-ttu-id="20b4a-120">Обновите экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20b4a-120">Update the instance.</span></span> <span data-ttu-id="20b4a-121">Для успешного вызова должен существовать экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20b4a-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="20b4a-122">2</span><span class="sxs-lookup"><span data-stu-id="20b4a-122">2</span></span> | <span data-ttu-id="20b4a-123">Создайте экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20b4a-123">Create the instance.</span></span> <span data-ttu-id="20b4a-124">Вызов завершается ошибкой, если экземпляр уже существует.</span><span class="sxs-lookup"><span data-stu-id="20b4a-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="20b4a-125">0x10</span><span class="sxs-lookup"><span data-stu-id="20b4a-125">0x10</span></span> | <span data-ttu-id="20b4a-126">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="20b4a-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="20b4a-127">окне Как правило, это значение `null`равно.</span><span class="sxs-lookup"><span data-stu-id="20b4a-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="20b4a-128">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные классы.</span><span class="sxs-lookup"><span data-stu-id="20b4a-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="20b4a-129">заполняет Если `null`значение равно, этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="20b4a-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="20b4a-130">Если `lFlags` параметр `WBEM_FLAG_RETURN_IMMEDIATELY`содержит, функция возвращает значение сразу `WBEM_S_NO_ERROR`с параметром.</span><span class="sxs-lookup"><span data-stu-id="20b4a-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="20b4a-131">Параметр `ppCallResult` получает указатель на новый объект [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult).</span><span class="sxs-lookup"><span data-stu-id="20b4a-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="20b4a-132">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="20b4a-132">Return value</span></span>

<span data-ttu-id="20b4a-133">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="20b4a-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="20b4a-134">Константа</span><span class="sxs-lookup"><span data-stu-id="20b4a-134">Constant</span></span>  |<span data-ttu-id="20b4a-135">Значение</span><span class="sxs-lookup"><span data-stu-id="20b4a-135">Value</span></span>  |<span data-ttu-id="20b4a-136">Описание</span><span class="sxs-lookup"><span data-stu-id="20b4a-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="20b4a-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="20b4a-137">0x80041003</span></span> | <span data-ttu-id="20b4a-138">У пользователя нет разрешения на обновление экземпляра указанного класса.</span><span class="sxs-lookup"><span data-stu-id="20b4a-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="20b4a-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="20b4a-139">0x80041001</span></span> | <span data-ttu-id="20b4a-140">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="20b4a-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="20b4a-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="20b4a-141">0x80041010</span></span> | <span data-ttu-id="20b4a-142">Недопустимый класс, поддерживающий данный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20b4a-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="20b4a-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="20b4a-143">0x80041028</span></span> | <span data-ttu-id="20b4a-144">был указан для свойства, которое не может быть `null`, например, помечено квалификатором **индексирования** или NOT_NULL. `null`</span><span class="sxs-lookup"><span data-stu-id="20b4a-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="20b4a-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="20b4a-145">0x8004100f</span></span> | <span data-ttu-id="20b4a-146">Указан недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="20b4a-146">The specified instance is not valid.</span></span> <span data-ttu-id="20b4a-147">(Например, вызов `PutInstanceWmi` с классом возвращает это значение.)</span><span class="sxs-lookup"><span data-stu-id="20b4a-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="20b4a-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="20b4a-148">0x80041008</span></span> | <span data-ttu-id="20b4a-149">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="20b4a-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="20b4a-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="20b4a-150">0x80041019</span></span> | <span data-ttu-id="20b4a-151">Указан `WBEM_FLAG_CREATE_ONLY` флаг, но экземпляр уже существует.</span><span class="sxs-lookup"><span data-stu-id="20b4a-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="20b4a-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="20b4a-152">0x80041002</span></span> | <span data-ttu-id="20b4a-153">`WBEM_FLAG_UPDATE_ONLY`был указан в `lFlags`, но экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="20b4a-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="20b4a-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="20b4a-154">0x80041006</span></span> | <span data-ttu-id="20b4a-155">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="20b4a-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="20b4a-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="20b4a-156">0x80041033</span></span> | <span data-ttu-id="20b4a-157">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="20b4a-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="20b4a-158">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="20b4a-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="20b4a-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="20b4a-159">0x80041015</span></span> | <span data-ttu-id="20b4a-160">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="20b4a-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="20b4a-161">0</span><span class="sxs-lookup"><span data-stu-id="20b4a-161">0</span></span> | <span data-ttu-id="20b4a-162">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="20b4a-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="20b4a-163">Примечания</span><span class="sxs-lookup"><span data-stu-id="20b4a-163">Remarks</span></span>

<span data-ttu-id="20b4a-164">Эта функция заключает вызов метода [IWbemServices::P утинстанце](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .</span><span class="sxs-lookup"><span data-stu-id="20b4a-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="20b4a-165">`PutInstanceWmi` Функция поддерживает создание экземпляров и обновление только экземпляров существующих классов.</span><span class="sxs-lookup"><span data-stu-id="20b4a-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="20b4a-166">В зависимости от того, `pCtx` как задан параметр, обновляются либо некоторые, либо все свойства экземпляра.</span><span class="sxs-lookup"><span data-stu-id="20b4a-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="20b4a-167">Если экземпляр, на который указывает `pInst` , принадлежит подклассу, то управление Windows вызывает всех поставщиков, ответственных за классы, от которых наследуется подкласс.</span><span class="sxs-lookup"><span data-stu-id="20b4a-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="20b4a-168">Все эти поставщики должны быть выполнены для выполнения исходного `PutInstanceWmi` запроса.</span><span class="sxs-lookup"><span data-stu-id="20b4a-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="20b4a-169">Поставщик, поддерживающий самый верхний класс в иерархии, вызывается первым.</span><span class="sxs-lookup"><span data-stu-id="20b4a-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="20b4a-170">Порядок вызова продолжается с подклассом самого верхнего класса и продолжается сверху вниз до тех пор, пока Управление Windows не достигнет поставщика для класса, которому принадлежит экземпляр, `pInst`на который указывает.</span><span class="sxs-lookup"><span data-stu-id="20b4a-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="20b4a-171">Система управления Windows не вызывает поставщики для любого из дочерних классов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="20b4a-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="20b4a-172">Когда приложение должно обновить экземпляр, принадлежащий иерархии классов, `pInst` параметр должен указывать на экземпляр, содержащий свойства, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="20b4a-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="20b4a-173">То есть рассмотрим целевой экземпляр, принадлежащий **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="20b4a-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="20b4a-174">Экземпляр **ClassB** является производным от **класса**a, а **класс** a определяет свойство **prop**.</span><span class="sxs-lookup"><span data-stu-id="20b4a-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="20b4a-175">Если приложению требуется изменить значение свойства **prop** a в экземпляре **ClassB** , оно должно быть задано `pInst` для этого экземпляра, а не экземпляра **класса**a.</span><span class="sxs-lookup"><span data-stu-id="20b4a-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="20b4a-176">Вызов `PutInstanceWmi` в экземпляре абстрактного класса не допускается.</span><span class="sxs-lookup"><span data-stu-id="20b4a-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="20b4a-177">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="20b4a-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="20b4a-178">Требования</span><span class="sxs-lookup"><span data-stu-id="20b4a-178">Requirements</span></span>

<span data-ttu-id="20b4a-179">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20b4a-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="20b4a-180">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="20b4a-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="20b4a-181">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20b4a-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="20b4a-182">См. также</span><span class="sxs-lookup"><span data-stu-id="20b4a-182">See also</span></span>

- [<span data-ttu-id="20b4a-183">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="20b4a-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
