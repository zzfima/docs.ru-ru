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
ms.openlocfilehash: b33f31d69c64ce520580c29f1014c058c78d0953
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127356"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="ac26b-103">Функция Путинстанцевми</span><span class="sxs-lookup"><span data-stu-id="ac26b-103">PutInstanceWmi function</span></span>

<span data-ttu-id="ac26b-104">Создает или обновляет экземпляр существующего класса.</span><span class="sxs-lookup"><span data-stu-id="ac26b-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="ac26b-105">Экземпляр записывается в репозиторий WMI.</span><span class="sxs-lookup"><span data-stu-id="ac26b-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ac26b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac26b-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="ac26b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac26b-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="ac26b-108">окне Указатель на экземпляр, который необходимо записать.</span><span class="sxs-lookup"><span data-stu-id="ac26b-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="ac26b-109">окне Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="ac26b-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="ac26b-110">Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ac26b-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac26b-111">Константа</span><span class="sxs-lookup"><span data-stu-id="ac26b-111">Constant</span></span>  |<span data-ttu-id="ac26b-112">значения</span><span class="sxs-lookup"><span data-stu-id="ac26b-112">Value</span></span>  |<span data-ttu-id="ac26b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ac26b-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="ac26b-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="ac26b-114">0x20000</span></span> | <span data-ttu-id="ac26b-115">Если задано, Инструментарий WMI не сохраняет никаких квалификаторов с **измененной** разновидностью.</span><span class="sxs-lookup"><span data-stu-id="ac26b-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="ac26b-116">Если не задано, предполагается, что этот объект не локализован, а все квалификаторы хранятся в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="ac26b-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="ac26b-117">0</span><span class="sxs-lookup"><span data-stu-id="ac26b-117">0</span></span> | <span data-ttu-id="ac26b-118">Создайте экземпляр, если он не существует, или перезапишите его, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="ac26b-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="ac26b-119">1</span><span class="sxs-lookup"><span data-stu-id="ac26b-119">1</span></span> | <span data-ttu-id="ac26b-120">Обновите экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ac26b-120">Update the instance.</span></span> <span data-ttu-id="ac26b-121">Для успешного вызова должен существовать экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ac26b-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="ac26b-122">2</span><span class="sxs-lookup"><span data-stu-id="ac26b-122">2</span></span> | <span data-ttu-id="ac26b-123">Создайте экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ac26b-123">Create the instance.</span></span> <span data-ttu-id="ac26b-124">Вызов завершается ошибкой, если экземпляр уже существует.</span><span class="sxs-lookup"><span data-stu-id="ac26b-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="ac26b-125">0x10</span><span class="sxs-lookup"><span data-stu-id="ac26b-125">0x10</span></span> | <span data-ttu-id="ac26b-126">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="ac26b-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="ac26b-127">окне Как правило, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="ac26b-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="ac26b-128">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные классы.</span><span class="sxs-lookup"><span data-stu-id="ac26b-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="ac26b-129">заполняет Если `null`, этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="ac26b-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="ac26b-130">Если `lFlags` содержит `WBEM_FLAG_RETURN_IMMEDIATELY`, функция немедленно возвращает значение `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="ac26b-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="ac26b-131">Параметр `ppCallResult` получает указатель на новый объект [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult).</span><span class="sxs-lookup"><span data-stu-id="ac26b-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="ac26b-132">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac26b-132">Return value</span></span>

<span data-ttu-id="ac26b-133">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ac26b-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac26b-134">Константа</span><span class="sxs-lookup"><span data-stu-id="ac26b-134">Constant</span></span>  |<span data-ttu-id="ac26b-135">значения</span><span class="sxs-lookup"><span data-stu-id="ac26b-135">Value</span></span>  |<span data-ttu-id="ac26b-136">Описание</span><span class="sxs-lookup"><span data-stu-id="ac26b-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="ac26b-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="ac26b-137">0x80041003</span></span> | <span data-ttu-id="ac26b-138">У пользователя нет разрешения на обновление экземпляра указанного класса.</span><span class="sxs-lookup"><span data-stu-id="ac26b-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="ac26b-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ac26b-139">0x80041001</span></span> | <span data-ttu-id="ac26b-140">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac26b-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="ac26b-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="ac26b-141">0x80041010</span></span> | <span data-ttu-id="ac26b-142">Недопустимый класс, поддерживающий данный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ac26b-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="ac26b-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="ac26b-143">0x80041028</span></span> | <span data-ttu-id="ac26b-144">`null` был указан для свойства, которое не может быть `null`, например, которое помечено квалификатором **индексирования** или **NOT_NULL** .</span><span class="sxs-lookup"><span data-stu-id="ac26b-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="ac26b-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="ac26b-145">0x8004100f</span></span> | <span data-ttu-id="ac26b-146">Указан недопустимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ac26b-146">The specified instance is not valid.</span></span> <span data-ttu-id="ac26b-147">(Например, вызов `PutInstanceWmi` с классом возвращает это значение.)</span><span class="sxs-lookup"><span data-stu-id="ac26b-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ac26b-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ac26b-148">0x80041008</span></span> | <span data-ttu-id="ac26b-149">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="ac26b-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="ac26b-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="ac26b-150">0x80041019</span></span> | <span data-ttu-id="ac26b-151">Указан флаг `WBEM_FLAG_CREATE_ONLY`, но экземпляр уже существует.</span><span class="sxs-lookup"><span data-stu-id="ac26b-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="ac26b-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ac26b-152">0x80041002</span></span> | <span data-ttu-id="ac26b-153">`WBEM_FLAG_UPDATE_ONLY` был указан в `lFlags`, но экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="ac26b-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ac26b-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ac26b-154">0x80041006</span></span> | <span data-ttu-id="ac26b-155">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="ac26b-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="ac26b-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="ac26b-156">0x80041033</span></span> | <span data-ttu-id="ac26b-157">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="ac26b-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="ac26b-158">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="ac26b-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ac26b-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ac26b-159">0x80041015</span></span> | <span data-ttu-id="ac26b-160">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="ac26b-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ac26b-161">0</span><span class="sxs-lookup"><span data-stu-id="ac26b-161">0</span></span> | <span data-ttu-id="ac26b-162">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ac26b-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ac26b-163">Заметки</span><span class="sxs-lookup"><span data-stu-id="ac26b-163">Remarks</span></span>

<span data-ttu-id="ac26b-164">Эта функция заключает вызов метода [IWbemServices::P утинстанце](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .</span><span class="sxs-lookup"><span data-stu-id="ac26b-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="ac26b-165">Функция `PutInstanceWmi` поддерживает создание экземпляров и обновление только экземпляров существующих классов.</span><span class="sxs-lookup"><span data-stu-id="ac26b-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="ac26b-166">В зависимости от того, как задан параметр `pCtx`, обновляются либо некоторые, либо все свойства экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ac26b-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="ac26b-167">Когда экземпляр, на который указывает `pInst`, принадлежит подклассу, управление Windows вызывает всех поставщиков, ответственных за классы, от которых наследуется подкласс.</span><span class="sxs-lookup"><span data-stu-id="ac26b-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="ac26b-168">Все эти поставщики должны быть выполнены для того, чтобы исходный запрос на `PutInstanceWmi` был выполнен.</span><span class="sxs-lookup"><span data-stu-id="ac26b-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="ac26b-169">Поставщик, поддерживающий самый верхний класс в иерархии, вызывается первым.</span><span class="sxs-lookup"><span data-stu-id="ac26b-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="ac26b-170">Порядок вызова продолжается с подклассом самого верхнего класса и продолжается сверху вниз до тех пор, пока Управление Windows не достигнет поставщика для класса, которому принадлежит экземпляр, на который указывает `pInst`.</span><span class="sxs-lookup"><span data-stu-id="ac26b-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="ac26b-171">Система управления Windows не вызывает поставщики для любого из дочерних классов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ac26b-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="ac26b-172">Когда приложение должно обновить экземпляр, принадлежащий иерархии классов, параметр `pInst` должен указывать на экземпляр, содержащий свойства, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="ac26b-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="ac26b-173">То есть рассмотрим целевой экземпляр, принадлежащий **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="ac26b-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="ac26b-174">Экземпляр **ClassB** является производным от **класса**a, а **класс** a определяет свойство **prop**.</span><span class="sxs-lookup"><span data-stu-id="ac26b-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="ac26b-175">Если приложению требуется внести изменение в значение **prop** a в экземпляре **ClassB** , оно должно задать `pInst` для этого экземпляра, а не экземпляра **класса**a.</span><span class="sxs-lookup"><span data-stu-id="ac26b-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="ac26b-176">Вызов `PutInstanceWmi` в экземпляре абстрактного класса не допускается.</span><span class="sxs-lookup"><span data-stu-id="ac26b-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="ac26b-177">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="ac26b-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac26b-178">Требования</span><span class="sxs-lookup"><span data-stu-id="ac26b-178">Requirements</span></span>

<span data-ttu-id="ac26b-179">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac26b-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ac26b-180">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ac26b-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ac26b-181">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac26b-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ac26b-182">См. также</span><span class="sxs-lookup"><span data-stu-id="ac26b-182">See also</span></span>

- [<span data-ttu-id="ac26b-183">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="ac26b-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
