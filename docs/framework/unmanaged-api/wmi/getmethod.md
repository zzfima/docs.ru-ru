---
title: Функция GetMethod (Справочник по неуправляемым API)
description: Функция GetMethod получает сведения о методе.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a913de0ff20fba51295fd8282b58e3953be9bba2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773963"
---
# <a name="getmethod-function"></a><span data-ttu-id="2eb79-103">Функция GetMethod</span><span class="sxs-lookup"><span data-stu-id="2eb79-103">GetMethod function</span></span>
<span data-ttu-id="2eb79-104">Получает сведения об указанном методе.</span><span class="sxs-lookup"><span data-stu-id="2eb79-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="2eb79-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2eb79-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="2eb79-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2eb79-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2eb79-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="2eb79-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2eb79-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2eb79-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="2eb79-109">[in] Имя метода.</span><span class="sxs-lookup"><span data-stu-id="2eb79-109">[in] The method name.</span></span> <span data-ttu-id="2eb79-110">Этот параметр не может быть `null` и должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="2eb79-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="2eb79-111">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="2eb79-111">[in] Reserved.</span></span> <span data-ttu-id="2eb79-112">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="2eb79-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="2eb79-113">[out] Указатель на адрес [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляр, описывающий в paramteers методу.</span><span class="sxs-lookup"><span data-stu-id="2eb79-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="2eb79-114">Этот параметр учитывается, если он становится равным `null`.</span><span class="sxs-lookup"><span data-stu-id="2eb79-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="2eb79-115">[out] Указатель на адрес [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляр, описывающий выходные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="2eb79-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="2eb79-116">Этот параметр учитывается, если он становится равным `null`.</span><span class="sxs-lookup"><span data-stu-id="2eb79-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="2eb79-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2eb79-117">Return value</span></span>

<span data-ttu-id="2eb79-118">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="2eb79-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2eb79-119">Константа</span><span class="sxs-lookup"><span data-stu-id="2eb79-119">Constant</span></span>  |<span data-ttu-id="2eb79-120">Значение</span><span class="sxs-lookup"><span data-stu-id="2eb79-120">Value</span></span>  |<span data-ttu-id="2eb79-121">Описание</span><span class="sxs-lookup"><span data-stu-id="2eb79-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="2eb79-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="2eb79-122">0x80041002</span></span> | <span data-ttu-id="2eb79-123">Указанное свойство не найден.</span><span class="sxs-lookup"><span data-stu-id="2eb79-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2eb79-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2eb79-124">0x80041006</span></span> | <span data-ttu-id="2eb79-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="2eb79-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2eb79-126">0</span><span class="sxs-lookup"><span data-stu-id="2eb79-126">0</span></span> | <span data-ttu-id="2eb79-127">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="2eb79-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2eb79-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2eb79-128">Remarks</span></span>

<span data-ttu-id="2eb79-129">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="2eb79-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="2eb79-130">Можно установить Windows Management [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатель на `null` Если у метода нет входные параметры.</span><span class="sxs-lookup"><span data-stu-id="2eb79-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="2eb79-131">В `ppInSignature` и `ppOutSignature` описывают входным и выходным параметрами, соответственно, в виде свойств `IWbemClassObject` экземпляр системного класса [_Parameters](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="2eb79-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="2eb79-132">Свойства в `ppInsignature` именуются **Param *** n*, где *n* позиция параметра в сигнатуре метода (такие как `Param1`, `Param2`и т. д.).</span><span class="sxs-lookup"><span data-stu-id="2eb79-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="2eb79-133">Свойства в `ppOutSignature` также называются **Param *** n*, и возвращаемое значение называется **ReturnValue**.</span><span class="sxs-lookup"><span data-stu-id="2eb79-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="2eb79-134">Дополнительные сведения и пример см. в разделе [IWbemClassObject::GetMethod метод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="2eb79-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="2eb79-135">Требования</span><span class="sxs-lookup"><span data-stu-id="2eb79-135">Requirements</span></span>  
<span data-ttu-id="2eb79-136">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eb79-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eb79-137">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2eb79-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2eb79-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2eb79-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb79-139">См. также</span><span class="sxs-lookup"><span data-stu-id="2eb79-139">See also</span></span>  
[<span data-ttu-id="2eb79-140">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2eb79-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
