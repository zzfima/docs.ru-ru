---
title: Функция InheritsFrom (Справочник по неуправляемым API)
description: Функция InheritsFrom определяет ли класс или экземпляр является производным от определенного родительского класса.
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
ms.openlocfilehash: 4784e22d5a3eec031fbee00441958a62d66b52df
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199792"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="eb7a1-103">Функция InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="eb7a1-103">InheritsFrom function</span></span>
<span data-ttu-id="eb7a1-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="eb7a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb7a1-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="eb7a1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb7a1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="eb7a1-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="eb7a1-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="eb7a1-109">[in] Имя класса.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-109">[in] The name of the class.</span></span> <span data-ttu-id="eb7a1-110">`wszAncestor` должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="eb7a1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eb7a1-111">Return value</span></span>

<span data-ttu-id="eb7a1-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="eb7a1-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eb7a1-113">Константа</span><span class="sxs-lookup"><span data-stu-id="eb7a1-113">Constant</span></span>  |<span data-ttu-id="eb7a1-114">Значение</span><span class="sxs-lookup"><span data-stu-id="eb7a1-114">Value</span></span>  |<span data-ttu-id="eb7a1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="eb7a1-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="eb7a1-116">0</span><span class="sxs-lookup"><span data-stu-id="eb7a1-116">0</span></span> | <span data-ttu-id="eb7a1-117">Наследуется текущий объект из `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="eb7a1-118">1</span><span class="sxs-lookup"><span data-stu-id="eb7a1-118">1</span></span> | <span data-ttu-id="eb7a1-119">Текущий объект не наследует от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eb7a1-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eb7a1-120">0x80041008</span></span> | <span data-ttu-id="eb7a1-121">Свойство `wszAncestor` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="eb7a1-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb7a1-122">Remarks</span></span>

<span data-ttu-id="eb7a1-123">Эта функция создает оболочку для вызова [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) метод.</span><span class="sxs-lookup"><span data-stu-id="eb7a1-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="eb7a1-124">Требования</span><span class="sxs-lookup"><span data-stu-id="eb7a1-124">Requirements</span></span>  
 <span data-ttu-id="eb7a1-125">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb7a1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb7a1-126">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eb7a1-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="eb7a1-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eb7a1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb7a1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="eb7a1-128">See also</span></span>  
[<span data-ttu-id="eb7a1-129">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="eb7a1-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
