---
title: Функция GetObjectText (Справочник по неуправляемым API)
description: Функция GetObjectText возвращает текстовое отображение объекта на синтаксисе MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208323"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="32d2e-103">Функция GetObjectText</span><span class="sxs-lookup"><span data-stu-id="32d2e-103">GetObjectText function</span></span>
<span data-ttu-id="32d2e-104">Возвращает текстовое отображение объекта в синтаксисе формата управляемых объектов (MOF).</span><span class="sxs-lookup"><span data-stu-id="32d2e-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="32d2e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32d2e-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="32d2e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="32d2e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="32d2e-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="32d2e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="32d2e-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="32d2e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="32d2e-109">[in] Обычно 0.</span><span class="sxs-lookup"><span data-stu-id="32d2e-109">[in] Normally 0.</span></span> <span data-ttu-id="32d2e-110">Если `WBEM_FLAG_NO_FLAVORS` (или 0x1) указывается, квалификаторы включаются без распространения или flavor информации.</span><span class="sxs-lookup"><span data-stu-id="32d2e-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="32d2e-111">[out] Указатель на `null` на запись.</span><span class="sxs-lookup"><span data-stu-id="32d2e-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="32d2e-112">Возвращенное значение во вновь выделенный `BSTR` , содержащий синтаксис MOF для преобразования объекта.</span><span class="sxs-lookup"><span data-stu-id="32d2e-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="32d2e-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32d2e-113">Return value</span></span>

<span data-ttu-id="32d2e-114">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="32d2e-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="32d2e-115">Константа</span><span class="sxs-lookup"><span data-stu-id="32d2e-115">Constant</span></span>  |<span data-ttu-id="32d2e-116">Значение</span><span class="sxs-lookup"><span data-stu-id="32d2e-116">Value</span></span>  |<span data-ttu-id="32d2e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="32d2e-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="32d2e-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="32d2e-118">0x80041001</span></span> | <span data-ttu-id="32d2e-119">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="32d2e-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="32d2e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="32d2e-120">0x80041008</span></span> | <span data-ttu-id="32d2e-121">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="32d2e-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="32d2e-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="32d2e-122">0x80041006</span></span> | <span data-ttu-id="32d2e-123">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="32d2e-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="32d2e-124">0</span><span class="sxs-lookup"><span data-stu-id="32d2e-124">0</span></span> | <span data-ttu-id="32d2e-125">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="32d2e-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="32d2e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="32d2e-126">Remarks</span></span>

<span data-ttu-id="32d2e-127">Эта функция создает оболочку для вызова [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) метод.</span><span class="sxs-lookup"><span data-stu-id="32d2e-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="32d2e-128">Текст MOF, возвращаемый не содержит все сведения об объекте, но только достаточно информации для компилятора MOF иметь возможность повторного создания исходного объекта.</span><span class="sxs-lookup"><span data-stu-id="32d2e-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="32d2e-129">Например включены не распространяются квалификаторы или свойства родительского класса.</span><span class="sxs-lookup"><span data-stu-id="32d2e-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="32d2e-130">Для воссоздания текст параметра метода используется следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="32d2e-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="32d2e-131">Параметры являются resequenced в порядке их значения идентификатора.</span><span class="sxs-lookup"><span data-stu-id="32d2e-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="32d2e-132">Параметры, которые задаются в виде `[in]` и `[out]` объединяются в один параметр.</span><span class="sxs-lookup"><span data-stu-id="32d2e-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
`pstrObjectText` <span data-ttu-id="32d2e-133">должен быть указателем на `null` при вызове функции; оно не должно указывать на строку, которая является допустимым до вызова метода, поскольку указатель не быть освобождена.</span><span class="sxs-lookup"><span data-stu-id="32d2e-133">must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="32d2e-134">Требования</span><span class="sxs-lookup"><span data-stu-id="32d2e-134">Requirements</span></span>  
<span data-ttu-id="32d2e-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32d2e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d2e-136">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="32d2e-136">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="32d2e-137">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="32d2e-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32d2e-138">См. также</span><span class="sxs-lookup"><span data-stu-id="32d2e-138">See also</span></span>

- [<span data-ttu-id="32d2e-139">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="32d2e-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
