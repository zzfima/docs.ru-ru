---
title: "Функция GetObjectText (Справочник по неуправляемым API)"
description: "Функция GetObjectText возвращает текстовое отображение объекта на синтаксис MOF."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b47dc73bb9da71b0c8593aa5758179327d7572d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getobjecttext-function"></a><span data-ttu-id="83063-103">Функция GetObjectText</span><span class="sxs-lookup"><span data-stu-id="83063-103">GetObjectText function</span></span>
<span data-ttu-id="83063-104">Возвращает текстовое преобразования объекта в синтаксисе формата управляемых объектов (MOF).</span><span class="sxs-lookup"><span data-stu-id="83063-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="83063-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83063-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="83063-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83063-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="83063-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="83063-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="83063-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="83063-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="83063-109">[in] Обычно 0.</span><span class="sxs-lookup"><span data-stu-id="83063-109">[in] Normally 0.</span></span> <span data-ttu-id="83063-110">Если `WBEM_FLAG_NO_FLAVORS` (или 0x1) указан, включаются квалификаторы без сведений о распространении или версия.</span><span class="sxs-lookup"><span data-stu-id="83063-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="83063-111">[out] Указатель на `null` на запись.</span><span class="sxs-lookup"><span data-stu-id="83063-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="83063-112">Возвращенное значение вновь выделенный `BSTR` , содержащий синтаксис MOF для преобразования объекта.</span><span class="sxs-lookup"><span data-stu-id="83063-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="83063-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83063-113">Return value</span></span>

<span data-ttu-id="83063-114">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="83063-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="83063-115">Константа</span><span class="sxs-lookup"><span data-stu-id="83063-115">Constant</span></span>  |<span data-ttu-id="83063-116">Значение</span><span class="sxs-lookup"><span data-stu-id="83063-116">Value</span></span>  |<span data-ttu-id="83063-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="83063-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="83063-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="83063-118">0x80041001</span></span> | <span data-ttu-id="83063-119">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="83063-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="83063-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="83063-120">0x80041008</span></span> | <span data-ttu-id="83063-121">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="83063-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="83063-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="83063-122">0x80041006</span></span> | <span data-ttu-id="83063-123">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="83063-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="83063-124">0</span><span class="sxs-lookup"><span data-stu-id="83063-124">0</span></span> | <span data-ttu-id="83063-125">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="83063-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="83063-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="83063-126">Remarks</span></span>

<span data-ttu-id="83063-127">Эта функция создает оболочку для вызова [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="83063-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="83063-128">MOF-текст, возвращаемый не содержит все сведения об объекте, но только достаточно сведений для MOF-компилятору иметь возможность повторного создания исходного объекта.</span><span class="sxs-lookup"><span data-stu-id="83063-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="83063-129">Например включаются не распространенный квалификаторы или свойства родительского класса.</span><span class="sxs-lookup"><span data-stu-id="83063-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="83063-130">Для реконструкции текст параметрам метода используется следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="83063-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="83063-131">Параметры являются resequenced в порядке их значения идентификатора.</span><span class="sxs-lookup"><span data-stu-id="83063-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="83063-132">Параметры, которые задаются в виде `[in]` и `[out]` объединяются в один параметр.</span><span class="sxs-lookup"><span data-stu-id="83063-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="83063-133">`pstrObjectText`должен быть указателем на `null` при вызове функции; оно не должно указывать строку, которая является допустимым до вызова метода, поскольку указатель не будет освобождена.</span><span class="sxs-lookup"><span data-stu-id="83063-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="83063-134">Требования</span><span class="sxs-lookup"><span data-stu-id="83063-134">Requirements</span></span>  
<span data-ttu-id="83063-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83063-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83063-136">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="83063-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="83063-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="83063-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83063-138">См. также</span><span class="sxs-lookup"><span data-stu-id="83063-138">See also</span></span>  
[<span data-ttu-id="83063-139">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="83063-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
