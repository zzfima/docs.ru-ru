---
title: Функция BeginMethodEnumeration (Неуправляемая справка API)
description: Функция BeginMethodEnumeration начинает перечисление методов объекта
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 876f5810fffab7fa98cd4d46715e13569ab95f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175048"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="81b96-103">Функция BeginMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="81b96-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="81b96-104">Начинается перечисление методов, доступных для объекта.</span><span class="sxs-lookup"><span data-stu-id="81b96-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="81b96-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81b96-105">Syntax</span></span>  
  
```cpp
HRESULT BeginMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="81b96-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="81b96-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="81b96-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="81b96-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="81b96-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="81b96-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="81b96-109">(в) Ноль (0) для всех методов или флаг, опоглавяя область перечисления.</span><span class="sxs-lookup"><span data-stu-id="81b96-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="81b96-110">Следующие флаги определены в файле заголовка *WbemCli.h,* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="81b96-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="81b96-111">Постоянно</span><span class="sxs-lookup"><span data-stu-id="81b96-111">Constant</span></span>  |<span data-ttu-id="81b96-112">Значение</span><span class="sxs-lookup"><span data-stu-id="81b96-112">Value</span></span>  |<span data-ttu-id="81b96-113">Описание</span><span class="sxs-lookup"><span data-stu-id="81b96-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="81b96-114">0x10</span><span class="sxs-lookup"><span data-stu-id="81b96-114">0x10</span></span> | <span data-ttu-id="81b96-115">Ограничьте перечисление методами, определенными в самом классе.</span><span class="sxs-lookup"><span data-stu-id="81b96-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="81b96-116">0x20</span><span class="sxs-lookup"><span data-stu-id="81b96-116">0x20</span></span> | <span data-ttu-id="81b96-117">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="81b96-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="81b96-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81b96-118">Return value</span></span>

<span data-ttu-id="81b96-119">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="81b96-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="81b96-120">Постоянно</span><span class="sxs-lookup"><span data-stu-id="81b96-120">Constant</span></span>  |<span data-ttu-id="81b96-121">Значение</span><span class="sxs-lookup"><span data-stu-id="81b96-121">Value</span></span>  |<span data-ttu-id="81b96-122">Описание</span><span class="sxs-lookup"><span data-stu-id="81b96-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="81b96-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="81b96-123">0x80041008</span></span> | <span data-ttu-id="81b96-124">`lEnnumFlags`не является нулевым и не является одним из указанных флагов.</span><span class="sxs-lookup"><span data-stu-id="81b96-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="81b96-125">0</span><span class="sxs-lookup"><span data-stu-id="81b96-125">0</span></span> | <span data-ttu-id="81b96-126">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="81b96-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="81b96-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="81b96-127">Remarks</span></span>

<span data-ttu-id="81b96-128">Эта функция завершает вызов [методом IWbemClassObject::BeginMethodEnumeration.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)</span><span class="sxs-lookup"><span data-stu-id="81b96-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="81b96-129">Этот вызов метода поддерживается только в том случае, если текущий объект является определением класса.</span><span class="sxs-lookup"><span data-stu-id="81b96-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="81b96-130">Манипуляция методом недоступна в указателях [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) которые указывают на экземпляры.</span><span class="sxs-lookup"><span data-stu-id="81b96-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="81b96-131">Порядок, в котором перечислены методы, гарантированно является инвариантным для данного экземпляра [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="81b96-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="81b96-132">Требования</span><span class="sxs-lookup"><span data-stu-id="81b96-132">Requirements</span></span>  
 <span data-ttu-id="81b96-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b96-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b96-134">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="81b96-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="81b96-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="81b96-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b96-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81b96-136">See also</span></span>

- [<span data-ttu-id="81b96-137">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="81b96-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
