---
title: Функция клонирования (Справочник по неуправляемым API)
description: Функция клонирования возвращает новый объект, который является копией завершения текущей.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b027d26292b5d810d91932bac4ec8dee4b77661d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643290"
---
# <a name="clone-function"></a><span data-ttu-id="bcc2e-103">Функция clone</span><span class="sxs-lookup"><span data-stu-id="bcc2e-103">Clone function</span></span>
<span data-ttu-id="bcc2e-104">Возвращает новый объект, который является полным клоном текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bcc2e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcc2e-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="bcc2e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcc2e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bcc2e-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bcc2e-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="bcc2e-109">[out] Объект, который является полным одиночному из `ptr`.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="bcc2e-110">Этот аргумент не может быть `null` , если он получает копию текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="bcc2e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcc2e-111">Return value</span></span>

<span data-ttu-id="bcc2e-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="bcc2e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bcc2e-113">Константа</span><span class="sxs-lookup"><span data-stu-id="bcc2e-113">Constant</span></span>  |<span data-ttu-id="bcc2e-114">Значение</span><span class="sxs-lookup"><span data-stu-id="bcc2e-114">Value</span></span>  |<span data-ttu-id="bcc2e-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="bcc2e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="bcc2e-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bcc2e-116">0x80041001</span></span> | <span data-ttu-id="bcc2e-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bcc2e-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bcc2e-118">0x80041008</span></span> | <span data-ttu-id="bcc2e-119">`null` был указан в качестве параметра, и он не является допустимым при таком использовании.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bcc2e-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bcc2e-120">0x80041006</span></span> | <span data-ttu-id="bcc2e-121">Не хватает памяти доступен для клонирования объекта.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bcc2e-122">0</span><span class="sxs-lookup"><span data-stu-id="bcc2e-122">0</span></span> | <span data-ttu-id="bcc2e-123">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bcc2e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcc2e-124">Remarks</span></span>

<span data-ttu-id="bcc2e-125">Эта функция создает оболочку для вызова [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) метод.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="bcc2e-126">Клонированный объект является COM-объект, имеющий значение счетчика ссылок равно 1.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="bcc2e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="bcc2e-127">Requirements</span></span>  
 <span data-ttu-id="bcc2e-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcc2e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcc2e-129">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bcc2e-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bcc2e-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bcc2e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc2e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="bcc2e-131">See also</span></span>
- [<span data-ttu-id="bcc2e-132">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
