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
ms.openlocfilehash: 80faf1a5a6297f5b105fdb609366f6774f8692b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761648"
---
# <a name="clone-function"></a><span data-ttu-id="00c97-103">Функция Clone</span><span class="sxs-lookup"><span data-stu-id="00c97-103">Clone function</span></span>
<span data-ttu-id="00c97-104">Возвращает новый объект, который является полным клоном текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="00c97-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="00c97-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00c97-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="00c97-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="00c97-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="00c97-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="00c97-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="00c97-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="00c97-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="00c97-109">[out] Объект, который является полным одиночному из `ptr`.</span><span class="sxs-lookup"><span data-stu-id="00c97-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="00c97-110">Этот аргумент не может быть `null` , если он получает копию текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="00c97-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="00c97-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="00c97-111">Return value</span></span>

<span data-ttu-id="00c97-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="00c97-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="00c97-113">Константа</span><span class="sxs-lookup"><span data-stu-id="00c97-113">Constant</span></span>  |<span data-ttu-id="00c97-114">Значение</span><span class="sxs-lookup"><span data-stu-id="00c97-114">Value</span></span>  |<span data-ttu-id="00c97-115">Описание</span><span class="sxs-lookup"><span data-stu-id="00c97-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="00c97-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="00c97-116">0x80041001</span></span> | <span data-ttu-id="00c97-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="00c97-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="00c97-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="00c97-118">0x80041008</span></span> | <span data-ttu-id="00c97-119">`null` был указан в качестве параметра, и он не является допустимым при таком использовании.</span><span class="sxs-lookup"><span data-stu-id="00c97-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="00c97-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="00c97-120">0x80041006</span></span> | <span data-ttu-id="00c97-121">Не хватает памяти доступен для клонирования объекта.</span><span class="sxs-lookup"><span data-stu-id="00c97-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="00c97-122">0</span><span class="sxs-lookup"><span data-stu-id="00c97-122">0</span></span> | <span data-ttu-id="00c97-123">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="00c97-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="00c97-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="00c97-124">Remarks</span></span>

<span data-ttu-id="00c97-125">Эта функция создает оболочку для вызова [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) метод.</span><span class="sxs-lookup"><span data-stu-id="00c97-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="00c97-126">Клонированный объект является COM-объект, имеющий значение счетчика ссылок равно 1.</span><span class="sxs-lookup"><span data-stu-id="00c97-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="00c97-127">Требования</span><span class="sxs-lookup"><span data-stu-id="00c97-127">Requirements</span></span>  
 <span data-ttu-id="00c97-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00c97-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c97-129">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="00c97-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="00c97-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00c97-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c97-131">См. также</span><span class="sxs-lookup"><span data-stu-id="00c97-131">See also</span></span>

- [<span data-ttu-id="00c97-132">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="00c97-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
