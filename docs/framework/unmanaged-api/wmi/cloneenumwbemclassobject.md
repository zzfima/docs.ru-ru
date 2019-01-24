---
title: Функция CloneEnumWbemClassObject (Справочник по неуправляемым API)
description: Функция CloneEnumWbemClassObject создается копия логического перечислитель.
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
ms.openlocfilehash: 52edc72e3714ceaf8cc92f272da6a374eb324dad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661650"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="e69b3-103">Функция CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="e69b3-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="e69b3-104">Создает логическую копию перечислителя, сохраняя текущую позицию в перечислении.</span><span class="sxs-lookup"><span data-stu-id="e69b3-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e69b3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e69b3-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="e69b3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e69b3-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="e69b3-107">[out] Получает указатель на новый [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="e69b3-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`  
<span data-ttu-id="e69b3-108">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="e69b3-108">[in] The authorization level.</span></span>

<span data-ttu-id="e69b3-109">`impLevel` [in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="e69b3-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="e69b3-110">[out] Указатель на [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) экземпляра для клонирования.</span><span class="sxs-lookup"><span data-stu-id="e69b3-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="e69b3-111">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="e69b3-111">[in] The user name.</span></span> <span data-ttu-id="e69b3-112">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="e69b3-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="e69b3-113">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="e69b3-113">[in] The password.</span></span> <span data-ttu-id="e69b3-114">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="e69b3-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="e69b3-115">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="e69b3-115">[in] The domain name of the user.</span></span> <span data-ttu-id="e69b3-116">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="e69b3-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="e69b3-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e69b3-117">Return value</span></span>

<span data-ttu-id="e69b3-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e69b3-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e69b3-119">Константа</span><span class="sxs-lookup"><span data-stu-id="e69b3-119">Constant</span></span>  |<span data-ttu-id="e69b3-120">Значение</span><span class="sxs-lookup"><span data-stu-id="e69b3-120">Value</span></span>  |<span data-ttu-id="e69b3-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="e69b3-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="e69b3-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e69b3-122">0x80041001</span></span> | <span data-ttu-id="e69b3-123">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="e69b3-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e69b3-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e69b3-124">0x80041008</span></span> | <span data-ttu-id="e69b3-125">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="e69b3-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e69b3-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e69b3-126">0x80041006</span></span> | <span data-ttu-id="e69b3-127">Не хватает памяти завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="e69b3-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="e69b3-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="e69b3-128">0x80041015</span></span> | <span data-ttu-id="e69b3-129">Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="e69b3-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e69b3-130">0</span><span class="sxs-lookup"><span data-stu-id="e69b3-130">0</span></span> | <span data-ttu-id="e69b3-131">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="e69b3-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e69b3-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="e69b3-132">Remarks</span></span>

<span data-ttu-id="e69b3-133">Эта функция создает оболочку для вызова [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) метод.</span><span class="sxs-lookup"><span data-stu-id="e69b3-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="e69b3-134">Этот метод копирует только «оптимальных затрат».</span><span class="sxs-lookup"><span data-stu-id="e69b3-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="e69b3-135">Из-за динамической природы множество объектов CIM вполне возможно, что новый перечислитель не перечислить тот же набор объектов, что перечислитель источника.</span><span class="sxs-lookup"><span data-stu-id="e69b3-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="e69b3-136">Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="e69b3-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="e69b3-137">Пример</span><span class="sxs-lookup"><span data-stu-id="e69b3-137">Example</span></span>

<span data-ttu-id="e69b3-138">Например, см. в разделе [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) метод.</span><span class="sxs-lookup"><span data-stu-id="e69b3-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e69b3-139">Требования</span><span class="sxs-lookup"><span data-stu-id="e69b3-139">Requirements</span></span>  
 <span data-ttu-id="e69b3-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e69b3-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e69b3-141">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e69b3-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e69b3-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e69b3-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69b3-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e69b3-143">See also</span></span>
- [<span data-ttu-id="e69b3-144">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e69b3-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
