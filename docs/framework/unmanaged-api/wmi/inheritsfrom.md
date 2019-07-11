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
ms.openlocfilehash: 5c04a08c9712359453b9c5a9d136e22e1de8648a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746507"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="db2eb-103">Функция InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="db2eb-103">InheritsFrom function</span></span>
<span data-ttu-id="db2eb-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="db2eb-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="db2eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db2eb-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="db2eb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="db2eb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="db2eb-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="db2eb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="db2eb-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="db2eb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="db2eb-109">[in] Имя класса.</span><span class="sxs-lookup"><span data-stu-id="db2eb-109">[in] The name of the class.</span></span> <span data-ttu-id="db2eb-110">`wszAncestor` должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="db2eb-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="db2eb-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="db2eb-111">Return value</span></span>

<span data-ttu-id="db2eb-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="db2eb-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="db2eb-113">Константа</span><span class="sxs-lookup"><span data-stu-id="db2eb-113">Constant</span></span>  |<span data-ttu-id="db2eb-114">Значение</span><span class="sxs-lookup"><span data-stu-id="db2eb-114">Value</span></span>  |<span data-ttu-id="db2eb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="db2eb-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="db2eb-116">0</span><span class="sxs-lookup"><span data-stu-id="db2eb-116">0</span></span> | <span data-ttu-id="db2eb-117">Наследуется текущий объект из `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="db2eb-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="db2eb-118">1</span><span class="sxs-lookup"><span data-stu-id="db2eb-118">1</span></span> | <span data-ttu-id="db2eb-119">Текущий объект не наследует от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="db2eb-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="db2eb-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="db2eb-120">0x80041008</span></span> | <span data-ttu-id="db2eb-121">Свойство `wszAncestor` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="db2eb-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="db2eb-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="db2eb-122">Remarks</span></span>

<span data-ttu-id="db2eb-123">Эта функция создает оболочку для вызова [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) метод.</span><span class="sxs-lookup"><span data-stu-id="db2eb-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="db2eb-124">Требования</span><span class="sxs-lookup"><span data-stu-id="db2eb-124">Requirements</span></span>  
 <span data-ttu-id="db2eb-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db2eb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db2eb-126">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="db2eb-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="db2eb-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="db2eb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2eb-128">См. также</span><span class="sxs-lookup"><span data-stu-id="db2eb-128">See also</span></span>

- [<span data-ttu-id="db2eb-129">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="db2eb-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
