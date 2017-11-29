---
title: "Функция BeginMethodEnumeration (Справочник по неуправляемым API)"
description: "Функция BeginMethodEnumeration начинается перечисление методов объектов"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginMethodEnumeration
helpviewer_keywords: BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e44c432f9503f96ad4dab9e25b78e6dd148f94c
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="5c92e-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="5c92e-103">BeginEnumeration function</span></span>
<span data-ttu-id="5c92e-104">Начинает перечисление методов, доступных для объекта.</span><span class="sxs-lookup"><span data-stu-id="5c92e-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5c92e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c92e-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="5c92e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c92e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5c92e-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5c92e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5c92e-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5c92e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="5c92e-109">[in] Ноль (0) для всех методов или флаг, указывающий область перечисления.</span><span class="sxs-lookup"><span data-stu-id="5c92e-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="5c92e-110">Далее перечислены флаги определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5c92e-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="5c92e-111">Константа</span><span class="sxs-lookup"><span data-stu-id="5c92e-111">Constant</span></span>  |<span data-ttu-id="5c92e-112">Значение</span><span class="sxs-lookup"><span data-stu-id="5c92e-112">Value</span></span>  |<span data-ttu-id="5c92e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5c92e-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="5c92e-114">0x10</span><span class="sxs-lookup"><span data-stu-id="5c92e-114">0x10</span></span> | <span data-ttu-id="5c92e-115">Ограничьте к методы, определенные в самом классе перечисления.</span><span class="sxs-lookup"><span data-stu-id="5c92e-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="5c92e-116">0x20</span><span class="sxs-lookup"><span data-stu-id="5c92e-116">0x20</span></span> | <span data-ttu-id="5c92e-117">Ограничения перечисления для свойства, наследуемые из базовых классов.</span><span class="sxs-lookup"><span data-stu-id="5c92e-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="5c92e-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5c92e-118">Return value</span></span>

<span data-ttu-id="5c92e-119">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5c92e-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5c92e-120">Константа</span><span class="sxs-lookup"><span data-stu-id="5c92e-120">Constant</span></span>  |<span data-ttu-id="5c92e-121">Значение</span><span class="sxs-lookup"><span data-stu-id="5c92e-121">Value</span></span>  |<span data-ttu-id="5c92e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5c92e-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5c92e-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5c92e-123">0x80041008</span></span> | <span data-ttu-id="5c92e-124">`lEnnumFlags`не равно нулю и не является одним из указанных флагов.</span><span class="sxs-lookup"><span data-stu-id="5c92e-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5c92e-125">0</span><span class="sxs-lookup"><span data-stu-id="5c92e-125">0</span></span> | <span data-ttu-id="5c92e-126">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="5c92e-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5c92e-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c92e-127">Remarks</span></span>

<span data-ttu-id="5c92e-128">Эта функция создает оболочку для вызова [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="5c92e-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="5c92e-129">Вызов этого метода поддерживается только в том случае, если текущий объект является определением класса.</span><span class="sxs-lookup"><span data-stu-id="5c92e-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="5c92e-130">Метод обработки не доступен из [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) указателей, указывающих на экземпляры.</span><span class="sxs-lookup"><span data-stu-id="5c92e-130">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to instances.</span></span> <span data-ttu-id="5c92e-131">Порядок, в котором перечисляются методы обязательно является инвариантным для заданного экземпляра [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c92e-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="5c92e-132">Требования</span><span class="sxs-lookup"><span data-stu-id="5c92e-132">Requirements</span></span>  
 <span data-ttu-id="5c92e-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c92e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c92e-134">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5c92e-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5c92e-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5c92e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c92e-136">См. также</span><span class="sxs-lookup"><span data-stu-id="5c92e-136">See also</span></span>  
[<span data-ttu-id="5c92e-137">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5c92e-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
