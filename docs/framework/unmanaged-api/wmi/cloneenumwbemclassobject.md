---
title: Функция Клонинумвбемклассобжект (Справочник по неуправляемым API)
description: Функция Клонинумвбемклассобжект создает логическую копию перечислителя.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605314f94fd82d2a2cd7be105dde9e273f607bc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798698"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="cc749-103">Функция CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="cc749-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="cc749-104">Создает логическую копию перечислителя, сохраняя текущую позицию в перечислении.</span><span class="sxs-lookup"><span data-stu-id="cc749-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cc749-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc749-105">Syntax</span></span>

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```

## <a name="parameters"></a><span data-ttu-id="cc749-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc749-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="cc749-107">заполняет Получает указатель на новый [иенумвбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="cc749-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="cc749-108">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="cc749-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="cc749-109">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="cc749-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="cc749-110">заполняет Указатель на экземпляр [иенумвбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) для клонирования.</span><span class="sxs-lookup"><span data-stu-id="cc749-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="cc749-111">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc749-111">[in] The user name.</span></span> <span data-ttu-id="cc749-112">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="cc749-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="cc749-113">окне Пароль.</span><span class="sxs-lookup"><span data-stu-id="cc749-113">[in] The password.</span></span> <span data-ttu-id="cc749-114">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="cc749-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="cc749-115">`strAuthority`\ [in] доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc749-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="cc749-116">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="cc749-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="cc749-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cc749-117">Return value</span></span>

<span data-ttu-id="cc749-118">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="cc749-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cc749-119">Константа</span><span class="sxs-lookup"><span data-stu-id="cc749-119">Constant</span></span>  |<span data-ttu-id="cc749-120">Значение</span><span class="sxs-lookup"><span data-stu-id="cc749-120">Value</span></span>  |<span data-ttu-id="cc749-121">Описание</span><span class="sxs-lookup"><span data-stu-id="cc749-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="cc749-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cc749-122">0x80041001</span></span> | <span data-ttu-id="cc749-123">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="cc749-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cc749-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cc749-124">0x80041008</span></span> | <span data-ttu-id="cc749-125">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="cc749-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cc749-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cc749-126">0x80041006</span></span> | <span data-ttu-id="cc749-127">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="cc749-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="cc749-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="cc749-128">0x80041015</span></span> | <span data-ttu-id="cc749-129">Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="cc749-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cc749-130">0</span><span class="sxs-lookup"><span data-stu-id="cc749-130">0</span></span> | <span data-ttu-id="cc749-131">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="cc749-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="cc749-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc749-132">Remarks</span></span>

<span data-ttu-id="cc749-133">Эта функция заключает в оболочку вызов метода [иенумвбемклассобжект:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="cc749-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="cc749-134">Этот метод делает только «наилучшую» копию.</span><span class="sxs-lookup"><span data-stu-id="cc749-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="cc749-135">Из-за динамической природы многих объектов CIM возможно, что новый перечислитель не перечисляет тот же набор объектов, что и перечислитель источника.</span><span class="sxs-lookup"><span data-stu-id="cc749-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="cc749-136">Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="cc749-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="cc749-137">Пример</span><span class="sxs-lookup"><span data-stu-id="cc749-137">Example</span></span>

<span data-ttu-id="cc749-138">Пример см. в описании метода [иенумвбемклассобжект:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="cc749-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc749-139">Требования</span><span class="sxs-lookup"><span data-stu-id="cc749-139">Requirements</span></span>
 <span data-ttu-id="cc749-140">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc749-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="cc749-141">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="cc749-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="cc749-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cc749-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cc749-143">См. также</span><span class="sxs-lookup"><span data-stu-id="cc749-143">See also</span></span>

- [<span data-ttu-id="cc749-144">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="cc749-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
