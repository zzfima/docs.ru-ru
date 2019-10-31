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
ms.openlocfilehash: 6bda63377251e3a208dfb1620896535ccdf8ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127430"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="8df67-103">Функция раскрывшемся</span><span class="sxs-lookup"><span data-stu-id="8df67-103">InheritsFrom function</span></span>
<span data-ttu-id="8df67-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="8df67-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8df67-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8df67-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="8df67-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8df67-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8df67-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="8df67-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8df67-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="8df67-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="8df67-109">окне Имя класса.</span><span class="sxs-lookup"><span data-stu-id="8df67-109">[in] The name of the class.</span></span> <span data-ttu-id="8df67-110">`wszAncestor` должен указывать на допустимое `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="8df67-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8df67-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8df67-111">Return value</span></span>

<span data-ttu-id="8df67-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8df67-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8df67-113">Константа</span><span class="sxs-lookup"><span data-stu-id="8df67-113">Constant</span></span>  |<span data-ttu-id="8df67-114">значения</span><span class="sxs-lookup"><span data-stu-id="8df67-114">Value</span></span>  |<span data-ttu-id="8df67-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8df67-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8df67-116">0</span><span class="sxs-lookup"><span data-stu-id="8df67-116">0</span></span> | <span data-ttu-id="8df67-117">Текущий объект наследуется от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="8df67-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="8df67-118">1</span><span class="sxs-lookup"><span data-stu-id="8df67-118">1</span></span> | <span data-ttu-id="8df67-119">Текущий объект не наследуется от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="8df67-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8df67-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8df67-120">0x80041008</span></span> | <span data-ttu-id="8df67-121">Свойство `wszAncestor` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="8df67-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="8df67-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="8df67-122">Remarks</span></span>

<span data-ttu-id="8df67-123">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: раскрывшемся](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="8df67-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8df67-124">Требования</span><span class="sxs-lookup"><span data-stu-id="8df67-124">Requirements</span></span>  
 <span data-ttu-id="8df67-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8df67-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8df67-126">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="8df67-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8df67-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8df67-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df67-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8df67-128">See also</span></span>

- [<span data-ttu-id="8df67-129">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="8df67-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
