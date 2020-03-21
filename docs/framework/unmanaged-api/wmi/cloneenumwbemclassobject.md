---
title: Функция CloneEnumWbemClassObject (Неуправляемая справка API)
description: Функция CloneEnumWbemClassObject является логической копией регистратора.
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
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175022"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="e0f0a-103">Функция CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="e0f0a-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="e0f0a-104">Создает логическую копию перечислителя, сохраняя текущую позицию в перечислении.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e0f0a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0f0a-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="e0f0a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0f0a-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="e0f0a-107">(ваут) Получает указатель на новый [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="e0f0a-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="e0f0a-108">(в) Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="e0f0a-109">(в) Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="e0f0a-110">(ваут) Указатель на экземпляр [IEnumWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) который будет клонирован.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="e0f0a-111">(в) Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-111">[in] The user name.</span></span> <span data-ttu-id="e0f0a-112">Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="e0f0a-113">(в) Пароль.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-113">[in] The password.</span></span> <span data-ttu-id="e0f0a-114">Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="e0f0a-115">(в) Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-115">[in] The domain name of the user.</span></span> <span data-ttu-id="e0f0a-116">Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="e0f0a-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0f0a-117">Return value</span></span>

<span data-ttu-id="e0f0a-118">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e0f0a-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e0f0a-119">Постоянно</span><span class="sxs-lookup"><span data-stu-id="e0f0a-119">Constant</span></span>  |<span data-ttu-id="e0f0a-120">Значение</span><span class="sxs-lookup"><span data-stu-id="e0f0a-120">Value</span></span>  |<span data-ttu-id="e0f0a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e0f0a-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="e0f0a-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e0f0a-122">0x80041001</span></span> | <span data-ttu-id="e0f0a-123">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e0f0a-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e0f0a-124">0x80041008</span></span> | <span data-ttu-id="e0f0a-125">Параметр недействителен.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e0f0a-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e0f0a-126">0x80041006</span></span> | <span data-ttu-id="e0f0a-127">Недостаточно памяти доступно завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="e0f0a-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="e0f0a-128">0x80041015</span></span> | <span data-ttu-id="e0f0a-129">Соединение удаленной процедуры (RPC) между текущим процессом и WMI не удалось.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e0f0a-130">0</span><span class="sxs-lookup"><span data-stu-id="e0f0a-130">0</span></span> | <span data-ttu-id="e0f0a-131">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e0f0a-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0f0a-132">Remarks</span></span>

<span data-ttu-id="e0f0a-133">Эта функция завершает вызов методом [IEnumWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="e0f0a-134">Этот метод делает только "лучшее усилие" копию.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="e0f0a-135">Из-за динамического характера многих объектов CIM, возможно, что новый регистратор не перечисляет тот же набор объектов, что и исходный регистратор.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="e0f0a-136">Если вызов функции не удается, вы можете получить дополнительную информацию об ошибке, позвонив в функцию [GetErrorInfo.](geterrorinfo.md)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="e0f0a-137">Пример</span><span class="sxs-lookup"><span data-stu-id="e0f0a-137">Example</span></span>

<span data-ttu-id="e0f0a-138">Например, [см.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0f0a-139">Требования</span><span class="sxs-lookup"><span data-stu-id="e0f0a-139">Requirements</span></span>
 <span data-ttu-id="e0f0a-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f0a-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="e0f0a-141">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e0f0a-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="e0f0a-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0f0a-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e0f0a-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0f0a-143">See also</span></span>

- [<span data-ttu-id="e0f0a-144">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
