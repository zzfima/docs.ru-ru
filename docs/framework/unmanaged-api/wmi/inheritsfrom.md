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
ms.openlocfilehash: 0d2af1b41f47a3906c0e573c104847aa3ff36cf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158435"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="c04f2-103">Функция InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="c04f2-103">InheritsFrom function</span></span>
<span data-ttu-id="c04f2-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="c04f2-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c04f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c04f2-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="c04f2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c04f2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c04f2-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="c04f2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c04f2-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c04f2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="c04f2-109">[in] Имя класса.</span><span class="sxs-lookup"><span data-stu-id="c04f2-109">[in] The name of the class.</span></span> `wszAncestor` <span data-ttu-id="c04f2-110">должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="c04f2-110">must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c04f2-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c04f2-111">Return value</span></span>

<span data-ttu-id="c04f2-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="c04f2-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c04f2-113">Константа</span><span class="sxs-lookup"><span data-stu-id="c04f2-113">Constant</span></span>  |<span data-ttu-id="c04f2-114">Значение</span><span class="sxs-lookup"><span data-stu-id="c04f2-114">Value</span></span>  |<span data-ttu-id="c04f2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c04f2-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c04f2-116">0</span><span class="sxs-lookup"><span data-stu-id="c04f2-116">0</span></span> | <span data-ttu-id="c04f2-117">Наследуется текущий объект из `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="c04f2-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="c04f2-118">1</span><span class="sxs-lookup"><span data-stu-id="c04f2-118">1</span></span> | <span data-ttu-id="c04f2-119">Текущий объект не наследует от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="c04f2-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c04f2-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c04f2-120">0x80041008</span></span> | `wszAncestor` <span data-ttu-id="c04f2-121">— `null`.</span><span class="sxs-lookup"><span data-stu-id="c04f2-121">is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c04f2-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="c04f2-122">Remarks</span></span>

<span data-ttu-id="c04f2-123">Эта функция создает оболочку для вызова [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) метод.</span><span class="sxs-lookup"><span data-stu-id="c04f2-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c04f2-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c04f2-124">Requirements</span></span>  
 <span data-ttu-id="c04f2-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c04f2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c04f2-126">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c04f2-126">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="c04f2-127">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c04f2-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c04f2-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c04f2-128">See also</span></span>

- [<span data-ttu-id="c04f2-129">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="c04f2-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
