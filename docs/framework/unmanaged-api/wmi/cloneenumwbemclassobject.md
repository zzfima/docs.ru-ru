---
title: "Функция CloneEnumWbemClassObject (Справочник по неуправляемым API)"
description: "Функция CloneEnumWbemClassObject делает логическую копию перечислителя."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22bcf2731ff682bf538858fc66a7a94be7f5d7df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="9b48a-103">Функция CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="9b48a-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="9b48a-104">Создается копия логического перечислителя, сохраняя его текущую позицию в перечислении.</span><span class="sxs-lookup"><span data-stu-id="9b48a-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9b48a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b48a-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="9b48a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b48a-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="9b48a-107">[out] Получает указатель на новый [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="9b48a-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="9b48a-108">[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="9b48a-108">[in] The authorization level.</span></span>

<span data-ttu-id="9b48a-109">`impLevel`[in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="9b48a-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="9b48a-110">[out] Указатель на [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) экземпляра для клонирования.</span><span class="sxs-lookup"><span data-stu-id="9b48a-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="9b48a-111">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="9b48a-111">[in] The user name.</span></span> <span data-ttu-id="9b48a-112">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="9b48a-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="9b48a-113">[in] Пароль.</span><span class="sxs-lookup"><span data-stu-id="9b48a-113">[in] The password.</span></span> <span data-ttu-id="9b48a-114">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="9b48a-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="9b48a-115">[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="9b48a-115">[in] The domain name of the user.</span></span> <span data-ttu-id="9b48a-116">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="9b48a-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="9b48a-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9b48a-117">Return value</span></span>

<span data-ttu-id="9b48a-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="9b48a-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9b48a-119">Константа</span><span class="sxs-lookup"><span data-stu-id="9b48a-119">Constant</span></span>  |<span data-ttu-id="9b48a-120">Значение</span><span class="sxs-lookup"><span data-stu-id="9b48a-120">Value</span></span>  |<span data-ttu-id="9b48a-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="9b48a-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="9b48a-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="9b48a-122">0x80041001</span></span> | <span data-ttu-id="9b48a-123">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="9b48a-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9b48a-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9b48a-124">0x80041008</span></span> | <span data-ttu-id="9b48a-125">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="9b48a-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9b48a-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9b48a-126">0x80041006</span></span> | <span data-ttu-id="9b48a-127">Не хватает памяти завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="9b48a-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="9b48a-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="9b48a-128">0x80041015</span></span> | <span data-ttu-id="9b48a-129">Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI.</span><span class="sxs-lookup"><span data-stu-id="9b48a-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9b48a-130">0</span><span class="sxs-lookup"><span data-stu-id="9b48a-130">0</span></span> | <span data-ttu-id="9b48a-131">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="9b48a-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9b48a-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b48a-132">Remarks</span></span>

<span data-ttu-id="9b48a-133">Эта функция создает оболочку для вызова [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="9b48a-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="9b48a-134">Этот метод копирует только «наилучшим возможным образом».</span><span class="sxs-lookup"><span data-stu-id="9b48a-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="9b48a-135">Из-за динамической природы многих объектов CIM возможна новый перечислитель не выполняет перечисление тот же набор объектов, что перечислителя источника.</span><span class="sxs-lookup"><span data-stu-id="9b48a-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="9b48a-136">При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="9b48a-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="9b48a-137">Пример</span><span class="sxs-lookup"><span data-stu-id="9b48a-137">Example</span></span>

<span data-ttu-id="9b48a-138">Пример см. в разделе [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="9b48a-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b48a-139">Требования</span><span class="sxs-lookup"><span data-stu-id="9b48a-139">Requirements</span></span>  
 <span data-ttu-id="9b48a-140">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b48a-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b48a-141">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9b48a-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9b48a-142">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b48a-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b48a-143">См. также</span><span class="sxs-lookup"><span data-stu-id="9b48a-143">See also</span></span>  
[<span data-ttu-id="9b48a-144">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="9b48a-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
