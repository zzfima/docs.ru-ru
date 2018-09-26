---
title: Функция DeleteMethod (Справочник по неуправляемым API)
description: Функция DeleteMethod Удаляет указанный метод из определения класса CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5996ce41c80cb54c4fcb9104c2993c85bcc2b466
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47192304"
---
# <a name="deletemethod-function"></a><span data-ttu-id="4eaf2-103">Функция DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="4eaf2-103">DeleteMethod function</span></span>
<span data-ttu-id="4eaf2-104">Удаляет указанный метод из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4eaf2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4eaf2-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4eaf2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4eaf2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4eaf2-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4eaf2-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="4eaf2-109">[in] Имя метода для удаления из класса в таблицу.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="4eaf2-110">`wszName` должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="4eaf2-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4eaf2-111">Return value</span></span>

<span data-ttu-id="4eaf2-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4eaf2-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4eaf2-113">Константа</span><span class="sxs-lookup"><span data-stu-id="4eaf2-113">Constant</span></span>  |<span data-ttu-id="4eaf2-114">Значение</span><span class="sxs-lookup"><span data-stu-id="4eaf2-114">Value</span></span>  |<span data-ttu-id="4eaf2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4eaf2-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="4eaf2-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4eaf2-116">0x80041002</span></span> | <span data-ttu-id="4eaf2-117">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4eaf2-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4eaf2-118">0x80041006</span></span> | <span data-ttu-id="4eaf2-119">Не хватает памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4eaf2-120">0</span><span class="sxs-lookup"><span data-stu-id="4eaf2-120">0</span></span> | <span data-ttu-id="4eaf2-121">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4eaf2-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="4eaf2-122">Remarks</span></span>

<span data-ttu-id="4eaf2-123">Эта функция создает оболочку для вызова [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) метод.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="4eaf2-124">Удаление метода не поддерживается для [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатели, которые указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="4eaf2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="4eaf2-125">Requirements</span></span>  
 <span data-ttu-id="4eaf2-126">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eaf2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eaf2-127">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4eaf2-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4eaf2-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eaf2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4eaf2-129">See also</span></span>  
[<span data-ttu-id="4eaf2-130">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4eaf2-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
