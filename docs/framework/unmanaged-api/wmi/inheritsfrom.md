---
title: Функция раскрывшемся (Справочник по неуправляемым API)
description: Функция раскрывшемся определяет, является ли класс или экземпляр производным от конкретного родительского класса.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c32c54ec56ea0fe4f4039ca6438a91338edbadb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798450"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="3e7d0-103">Функция раскрывшемся</span><span class="sxs-lookup"><span data-stu-id="3e7d0-103">InheritsFrom function</span></span>
<span data-ttu-id="3e7d0-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3e7d0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e7d0-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="3e7d0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e7d0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3e7d0-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3e7d0-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="3e7d0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="3e7d0-109">окне Имя класса.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-109">[in] The name of the class.</span></span> <span data-ttu-id="3e7d0-110">`wszAncestor`должен указывать на допустимое `LPCWSTR`значение.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3e7d0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e7d0-111">Return value</span></span>

<span data-ttu-id="3e7d0-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="3e7d0-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3e7d0-113">Константа</span><span class="sxs-lookup"><span data-stu-id="3e7d0-113">Constant</span></span>  |<span data-ttu-id="3e7d0-114">Значение</span><span class="sxs-lookup"><span data-stu-id="3e7d0-114">Value</span></span>  |<span data-ttu-id="3e7d0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3e7d0-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3e7d0-116">0</span><span class="sxs-lookup"><span data-stu-id="3e7d0-116">0</span></span> | <span data-ttu-id="3e7d0-117">Текущий объект наследует от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="3e7d0-118">1</span><span class="sxs-lookup"><span data-stu-id="3e7d0-118">1</span></span> | <span data-ttu-id="3e7d0-119">Текущий объект не наследует от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3e7d0-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3e7d0-120">0x80041008</span></span> | <span data-ttu-id="3e7d0-121">Свойство `wszAncestor` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="3e7d0-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3e7d0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e7d0-122">Remarks</span></span>

<span data-ttu-id="3e7d0-123">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: раскрывшемся](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="3e7d0-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e7d0-124">Требования</span><span class="sxs-lookup"><span data-stu-id="3e7d0-124">Requirements</span></span>  
 <span data-ttu-id="3e7d0-125">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e7d0-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e7d0-126">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3e7d0-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3e7d0-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e7d0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7d0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3e7d0-128">See also</span></span>

- [<span data-ttu-id="3e7d0-129">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="3e7d0-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
