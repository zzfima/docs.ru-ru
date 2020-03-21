---
title: Функция клона (Неуправляемая ссылка API)
description: Функция клона возвращает новый объект, который является полным клоном текущего.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176855"
---
# <a name="clone-function"></a><span data-ttu-id="250cb-103">Функция Clone</span><span class="sxs-lookup"><span data-stu-id="250cb-103">Clone function</span></span>
<span data-ttu-id="250cb-104">Возвращает новый объект, который является полным клоном текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="250cb-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="250cb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="250cb-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="250cb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="250cb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="250cb-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="250cb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="250cb-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="250cb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="250cb-109">(ваут) Новый объект, который является `ptr`полным одиноким .</span><span class="sxs-lookup"><span data-stu-id="250cb-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="250cb-110">Этот аргумент `null` не может быть, если он получает копию текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="250cb-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="250cb-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="250cb-111">Return value</span></span>

<span data-ttu-id="250cb-112">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="250cb-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="250cb-113">Постоянно</span><span class="sxs-lookup"><span data-stu-id="250cb-113">Constant</span></span>  |<span data-ttu-id="250cb-114">Значение</span><span class="sxs-lookup"><span data-stu-id="250cb-114">Value</span></span>  |<span data-ttu-id="250cb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="250cb-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="250cb-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="250cb-116">0x80041001</span></span> | <span data-ttu-id="250cb-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="250cb-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="250cb-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="250cb-118">0x80041008</span></span> | <span data-ttu-id="250cb-119">`null`был указан в качестве параметра, и это не является законным в этом использовании.</span><span class="sxs-lookup"><span data-stu-id="250cb-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="250cb-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="250cb-120">0x80041006</span></span> | <span data-ttu-id="250cb-121">Недостаточно памяти для клонирования объекта.</span><span class="sxs-lookup"><span data-stu-id="250cb-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="250cb-122">0</span><span class="sxs-lookup"><span data-stu-id="250cb-122">0</span></span> | <span data-ttu-id="250cb-123">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="250cb-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="250cb-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="250cb-124">Remarks</span></span>

<span data-ttu-id="250cb-125">Эта функция завершает вызов [методом IWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="250cb-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="250cb-126">Клонированный объект — объект COM с числом ссылок 1.</span><span class="sxs-lookup"><span data-stu-id="250cb-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="250cb-127">Требования</span><span class="sxs-lookup"><span data-stu-id="250cb-127">Requirements</span></span>  
 <span data-ttu-id="250cb-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="250cb-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="250cb-129">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="250cb-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="250cb-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="250cb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="250cb-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="250cb-131">See also</span></span>

- [<span data-ttu-id="250cb-132">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="250cb-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
