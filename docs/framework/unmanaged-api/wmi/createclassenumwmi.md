---
title: Функция Креатеклассенумвми (Справочник по неуправляемым API)
description: Функция Креатеклассенумвми Возвращает перечислитель для всех классов, удовлетворяющих заданным условиям.
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
ms.openlocfilehash: 1d637479bd140e635ee647a1e30d03343d8b0dcd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107523"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="f09c7-103">Функция Креатеклассенумвми</span><span class="sxs-lookup"><span data-stu-id="f09c7-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="f09c7-104">Возвращает перечислитель для всех классов, которые удовлетворяют указанным критериям выбора.</span><span class="sxs-lookup"><span data-stu-id="f09c7-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f09c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f09c7-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="f09c7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f09c7-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="f09c7-107">окне Если не `null` или пусто, задает имя родительского класса. перечислитель возвращает только подклассы этого класса.</span><span class="sxs-lookup"><span data-stu-id="f09c7-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="f09c7-108">Если он `null` или пуст и `lFlags` WBEM_FLAG_SHALLOW, возвращает только классы верхнего уровня (классы без родительского класса).</span><span class="sxs-lookup"><span data-stu-id="f09c7-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="f09c7-109">Если он `null` или пуст и `lFlags` `WBEM_FLAG_DEEP`, возвращает все классы в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f09c7-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="f09c7-110">окне Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="f09c7-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="f09c7-111">Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="f09c7-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f09c7-112">Константа</span><span class="sxs-lookup"><span data-stu-id="f09c7-112">Constant</span></span>  |<span data-ttu-id="f09c7-113">значения</span><span class="sxs-lookup"><span data-stu-id="f09c7-113">Value</span></span>  |<span data-ttu-id="f09c7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f09c7-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="f09c7-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="f09c7-115">0x20000</span></span> | <span data-ttu-id="f09c7-116">Если параметр задан, функция получает измененные квалификаторы, хранящиеся в локализованном пространстве имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="f09c7-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="f09c7-117">Если значение не задано, функция извлекает только квалификаторы, хранящиеся в пространстве имен immediate.</span><span class="sxs-lookup"><span data-stu-id="f09c7-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="f09c7-118">0</span><span class="sxs-lookup"><span data-stu-id="f09c7-118">0</span></span> | <span data-ttu-id="f09c7-119">Перечисление включает все подклассы в иерархии, но не этот класс.</span><span class="sxs-lookup"><span data-stu-id="f09c7-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="f09c7-120">1</span><span class="sxs-lookup"><span data-stu-id="f09c7-120">1</span></span> | <span data-ttu-id="f09c7-121">Перечисление включает только чистые экземпляры этого класса и исключает все экземпляры подклассов, которые предоставляют свойства, не найденные в этом классе.</span><span class="sxs-lookup"><span data-stu-id="f09c7-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="f09c7-122">0x10</span><span class="sxs-lookup"><span data-stu-id="f09c7-122">0x10</span></span> | <span data-ttu-id="f09c7-123">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="f09c7-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="f09c7-124">0x20</span><span class="sxs-lookup"><span data-stu-id="f09c7-124">0x20</span></span> | <span data-ttu-id="f09c7-125">Функция возвращает перечислитель только для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="f09c7-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="f09c7-126">Как правило, перечислители выполняются быстрее и используют меньше памяти, чем обычные перечислители, но не допускают вызовы для [клонирования](clone.md).</span><span class="sxs-lookup"><span data-stu-id="f09c7-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="f09c7-127">0</span><span class="sxs-lookup"><span data-stu-id="f09c7-127">0</span></span> | <span data-ttu-id="f09c7-128">Инструментарий WMI удерживает указатели на объекты в перечислении до их освобождения.</span><span class="sxs-lookup"><span data-stu-id="f09c7-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="f09c7-129">Для лучшей производительности рекомендуется использовать флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="f09c7-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="f09c7-130">окне Как правило, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f09c7-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="f09c7-131">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные классы.</span><span class="sxs-lookup"><span data-stu-id="f09c7-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="f09c7-132">заполняет Получает указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="f09c7-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="f09c7-133">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="f09c7-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="f09c7-134">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="f09c7-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="f09c7-135">окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="f09c7-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="f09c7-136">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="f09c7-136">[in] The user name.</span></span> <span data-ttu-id="f09c7-137">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="f09c7-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="f09c7-138">окне Пароль.</span><span class="sxs-lookup"><span data-stu-id="f09c7-138">[in] The password.</span></span> <span data-ttu-id="f09c7-139">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="f09c7-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="f09c7-140">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="f09c7-140">[in] The domain name of the user.</span></span> <span data-ttu-id="f09c7-141">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="f09c7-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="f09c7-142">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f09c7-142">Return value</span></span>

<span data-ttu-id="f09c7-143">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="f09c7-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f09c7-144">Константа</span><span class="sxs-lookup"><span data-stu-id="f09c7-144">Constant</span></span>  |<span data-ttu-id="f09c7-145">значения</span><span class="sxs-lookup"><span data-stu-id="f09c7-145">Value</span></span>  |<span data-ttu-id="f09c7-146">Описание</span><span class="sxs-lookup"><span data-stu-id="f09c7-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="f09c7-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="f09c7-147">0x80041003</span></span> | <span data-ttu-id="f09c7-148">Пользователь не имеет разрешения на просмотр одного или нескольких классов, которые может возвращать функция.</span><span class="sxs-lookup"><span data-stu-id="f09c7-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="f09c7-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f09c7-149">0x80041001</span></span> | <span data-ttu-id="f09c7-150">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f09c7-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="f09c7-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="f09c7-151">0x80041010</span></span> | <span data-ttu-id="f09c7-152">`strSuperClass` — не существует.</span><span class="sxs-lookup"><span data-stu-id="f09c7-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f09c7-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f09c7-153">0x80041008</span></span> | <span data-ttu-id="f09c7-154">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="f09c7-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f09c7-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f09c7-155">0x80041006</span></span> | <span data-ttu-id="f09c7-156">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="f09c7-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="f09c7-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="f09c7-157">0x80041033</span></span> | <span data-ttu-id="f09c7-158">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="f09c7-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="f09c7-159">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="f09c7-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="f09c7-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="f09c7-160">0x80041015</span></span> | <span data-ttu-id="f09c7-161">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="f09c7-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f09c7-162">0</span><span class="sxs-lookup"><span data-stu-id="f09c7-162">0</span></span> | <span data-ttu-id="f09c7-163">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f09c7-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="f09c7-164">Заметки</span><span class="sxs-lookup"><span data-stu-id="f09c7-164">Remarks</span></span>

<span data-ttu-id="f09c7-165">Эта функция заключает вызов метода [IWbemServices:: креатеклассенум](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) .</span><span class="sxs-lookup"><span data-stu-id="f09c7-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="f09c7-166">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="f09c7-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="f09c7-167">Требования</span><span class="sxs-lookup"><span data-stu-id="f09c7-167">Requirements</span></span>

<span data-ttu-id="f09c7-168">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f09c7-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f09c7-169">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f09c7-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="f09c7-170">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f09c7-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f09c7-171">См. также</span><span class="sxs-lookup"><span data-stu-id="f09c7-171">See also</span></span>

- [<span data-ttu-id="f09c7-172">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="f09c7-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
