---
title: Наследуетот функции (Неуправляемая ссылка API)
description: Функция InheritsFrom определяет, является ли класс или экземпляр производным от определенного родительского класса.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174944"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="9a8a6-103">Функция InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="9a8a6-103">InheritsFrom function</span></span>
<span data-ttu-id="9a8a6-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="9a8a6-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9a8a6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a8a6-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="9a8a6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a8a6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9a8a6-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="9a8a6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9a8a6-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="9a8a6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="9a8a6-109">(в) Название класса.</span><span class="sxs-lookup"><span data-stu-id="9a8a6-109">[in] The name of the class.</span></span> <span data-ttu-id="9a8a6-110">`wszAncestor`должны указать `LPCWSTR`на допустимый .</span><span class="sxs-lookup"><span data-stu-id="9a8a6-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9a8a6-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a8a6-111">Return value</span></span>

<span data-ttu-id="9a8a6-112">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="9a8a6-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9a8a6-113">Постоянно</span><span class="sxs-lookup"><span data-stu-id="9a8a6-113">Constant</span></span>  |<span data-ttu-id="9a8a6-114">Значение</span><span class="sxs-lookup"><span data-stu-id="9a8a6-114">Value</span></span>  |<span data-ttu-id="9a8a6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9a8a6-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9a8a6-116">0</span><span class="sxs-lookup"><span data-stu-id="9a8a6-116">0</span></span> | <span data-ttu-id="9a8a6-117">Текущий объект наследует от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="9a8a6-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="9a8a6-118">1</span><span class="sxs-lookup"><span data-stu-id="9a8a6-118">1</span></span> | <span data-ttu-id="9a8a6-119">Текущий объект не `wszAncestor`наследует от .</span><span class="sxs-lookup"><span data-stu-id="9a8a6-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9a8a6-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9a8a6-120">0x80041008</span></span> | <span data-ttu-id="9a8a6-121">Параметр `wszAncestor` равен `null`.</span><span class="sxs-lookup"><span data-stu-id="9a8a6-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="9a8a6-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a8a6-122">Remarks</span></span>

<span data-ttu-id="9a8a6-123">Эта функция обертывает вызов на [IWbemClassObject::НаследуетОт](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) метода.</span><span class="sxs-lookup"><span data-stu-id="9a8a6-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9a8a6-124">Требования</span><span class="sxs-lookup"><span data-stu-id="9a8a6-124">Requirements</span></span>  
 <span data-ttu-id="9a8a6-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a8a6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a8a6-126">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9a8a6-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9a8a6-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8a6-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8a6-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9a8a6-128">See also</span></span>

- [<span data-ttu-id="9a8a6-129">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="9a8a6-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
