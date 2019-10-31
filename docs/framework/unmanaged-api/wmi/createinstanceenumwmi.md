---
title: Функция Креатеинстанцеенумвми (Справочник по неуправляемым API)
description: Функция Креатеинстанцеенумвми Возвращает перечислитель, содержащий экземпляры указанного класса, соответствующие критериям выбора.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9ffa718be0e8b67471fdf8cb277df201388d2840
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130401"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="dac26-103">Функция Креатеинстанцеенумвми</span><span class="sxs-lookup"><span data-stu-id="dac26-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="dac26-104">Возвращает перечислитель, возвращающий экземпляры указанного класса в соответствии с заданными критериями выбора.</span><span class="sxs-lookup"><span data-stu-id="dac26-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="dac26-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dac26-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="dac26-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dac26-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="dac26-107">окне Имя класса, для которого нужны экземпляры.</span><span class="sxs-lookup"><span data-stu-id="dac26-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="dac26-108">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="dac26-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="dac26-109">окне Сочетание флагов, влияющих на поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="dac26-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="dac26-110">Следующие значения определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="dac26-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dac26-111">Константа</span><span class="sxs-lookup"><span data-stu-id="dac26-111">Constant</span></span>  |<span data-ttu-id="dac26-112">значения</span><span class="sxs-lookup"><span data-stu-id="dac26-112">Value</span></span>  |<span data-ttu-id="dac26-113">Описание</span><span class="sxs-lookup"><span data-stu-id="dac26-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="dac26-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="dac26-114">0x20000</span></span> | <span data-ttu-id="dac26-115">Если параметр задан, функция получает измененные квалификаторы, хранящиеся в локализованном пространстве имен языкового стандарта текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="dac26-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="dac26-116">Если значение не задано, функция извлекает только квалификаторы, хранящиеся в пространстве имен immediate.</span><span class="sxs-lookup"><span data-stu-id="dac26-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="dac26-117">0</span><span class="sxs-lookup"><span data-stu-id="dac26-117">0</span></span> | <span data-ttu-id="dac26-118">Перечисление включает в себя этот и все подклассы в иерархии.</span><span class="sxs-lookup"><span data-stu-id="dac26-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="dac26-119">1</span><span class="sxs-lookup"><span data-stu-id="dac26-119">1</span></span> | <span data-ttu-id="dac26-120">Перечисление включает только чистые экземпляры этого класса и исключает все экземпляры подклассов, которые предоставляют свойства, не найденные в этом классе.</span><span class="sxs-lookup"><span data-stu-id="dac26-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="dac26-121">0x10</span><span class="sxs-lookup"><span data-stu-id="dac26-121">0x10</span></span> | <span data-ttu-id="dac26-122">Флаг вызывает вызов семисинчронаус.</span><span class="sxs-lookup"><span data-stu-id="dac26-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="dac26-123">0x20</span><span class="sxs-lookup"><span data-stu-id="dac26-123">0x20</span></span> | <span data-ttu-id="dac26-124">Функция возвращает перечислитель только для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="dac26-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="dac26-125">Как правило, перечислители выполняются быстрее и используют меньше памяти, чем обычные перечислители, но не допускают вызовы для [клонирования](clone.md).</span><span class="sxs-lookup"><span data-stu-id="dac26-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="dac26-126">0</span><span class="sxs-lookup"><span data-stu-id="dac26-126">0</span></span> | <span data-ttu-id="dac26-127">Инструментарий WMI удерживает указатели на объекты в перечислении до их освобождения.</span><span class="sxs-lookup"><span data-stu-id="dac26-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="dac26-128">Для лучшей производительности рекомендуется использовать флаги `WBEM_FLAG_RETURN_IMMEDIATELY` и `WBEM_FLAG_FORWARD_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="dac26-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="dac26-129">окне Как правило, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="dac26-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="dac26-130">В противном случае он является указателем на экземпляр [ивбемконтекст](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) , который может использоваться поставщиком, который предоставляет запрошенные экземпляры.</span><span class="sxs-lookup"><span data-stu-id="dac26-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="dac26-131">заполняет Получает указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="dac26-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="dac26-132">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="dac26-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="dac26-133">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="dac26-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="dac26-134">окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , представляющий текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="dac26-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="dac26-135">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="dac26-135">[in] The user name.</span></span> <span data-ttu-id="dac26-136">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="dac26-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="dac26-137">окне Пароль.</span><span class="sxs-lookup"><span data-stu-id="dac26-137">[in] The password.</span></span> <span data-ttu-id="dac26-138">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="dac26-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="dac26-139">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="dac26-139">[in] The domain name of the user.</span></span> <span data-ttu-id="dac26-140">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="dac26-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="dac26-141">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dac26-141">Return value</span></span>

<span data-ttu-id="dac26-142">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="dac26-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dac26-143">Константа</span><span class="sxs-lookup"><span data-stu-id="dac26-143">Constant</span></span>  |<span data-ttu-id="dac26-144">значения</span><span class="sxs-lookup"><span data-stu-id="dac26-144">Value</span></span>  |<span data-ttu-id="dac26-145">Описание</span><span class="sxs-lookup"><span data-stu-id="dac26-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="dac26-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="dac26-146">0x80041003</span></span> | <span data-ttu-id="dac26-147">У пользователя нет разрешения на просмотр экземпляров указанного класса.</span><span class="sxs-lookup"><span data-stu-id="dac26-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="dac26-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="dac26-148">0x80041001</span></span> | <span data-ttu-id="dac26-149">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="dac26-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="dac26-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="dac26-150">0x80041010</span></span> | <span data-ttu-id="dac26-151">`strFilter` — не существует.</span><span class="sxs-lookup"><span data-stu-id="dac26-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="dac26-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="dac26-152">0x80041008</span></span> | <span data-ttu-id="dac26-153">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="dac26-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="dac26-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="dac26-154">0x80041006</span></span> | <span data-ttu-id="dac26-155">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="dac26-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="dac26-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="dac26-156">0x80041033</span></span> | <span data-ttu-id="dac26-157">Вероятно, Инструментарий WMI остановлен и перезапущен.</span><span class="sxs-lookup"><span data-stu-id="dac26-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="dac26-158">Снова вызовите [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="dac26-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="dac26-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="dac26-159">0x80041015</span></span> | <span data-ttu-id="dac26-160">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="dac26-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="dac26-161">0</span><span class="sxs-lookup"><span data-stu-id="dac26-161">0</span></span> | <span data-ttu-id="dac26-162">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="dac26-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="dac26-163">Заметки</span><span class="sxs-lookup"><span data-stu-id="dac26-163">Remarks</span></span>

<span data-ttu-id="dac26-164">Эта функция заключает вызов метода [IWbemServices:: креатеклассенум](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) .</span><span class="sxs-lookup"><span data-stu-id="dac26-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="dac26-165">Обратите внимание, что возвращаемый перечислитель может иметь нулевые элементы.</span><span class="sxs-lookup"><span data-stu-id="dac26-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="dac26-166">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="dac26-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="dac26-167">Требования</span><span class="sxs-lookup"><span data-stu-id="dac26-167">Requirements</span></span>

<span data-ttu-id="dac26-168">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dac26-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="dac26-169">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="dac26-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="dac26-170">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dac26-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dac26-171">См. также</span><span class="sxs-lookup"><span data-stu-id="dac26-171">See also</span></span>

- [<span data-ttu-id="dac26-172">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="dac26-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
