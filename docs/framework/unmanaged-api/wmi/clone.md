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
ms.openlocfilehash: bf9cca10a580af7991889de6993e931347fc27ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120966"
---
# <a name="clone-function"></a><span data-ttu-id="0a36e-103">Функция Clone</span><span class="sxs-lookup"><span data-stu-id="0a36e-103">Clone function</span></span>
<span data-ttu-id="0a36e-104">Возвращает новый объект, который является полным клоном текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="0a36e-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0a36e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a36e-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="0a36e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a36e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0a36e-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="0a36e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0a36e-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0a36e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="0a36e-109">[out] Объект, который является полным одиночному из `ptr`.</span><span class="sxs-lookup"><span data-stu-id="0a36e-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="0a36e-110">Этот аргумент не может быть `null` , если он получает копию текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="0a36e-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="0a36e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a36e-111">Return value</span></span>

<span data-ttu-id="0a36e-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="0a36e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0a36e-113">Константа</span><span class="sxs-lookup"><span data-stu-id="0a36e-113">Constant</span></span>  |<span data-ttu-id="0a36e-114">Значение</span><span class="sxs-lookup"><span data-stu-id="0a36e-114">Value</span></span>  |<span data-ttu-id="0a36e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0a36e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0a36e-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0a36e-116">0x80041001</span></span> | <span data-ttu-id="0a36e-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="0a36e-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0a36e-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0a36e-118">0x80041008</span></span> | `null` <span data-ttu-id="0a36e-119">был указан в качестве параметра, и он не является допустимым при таком использовании.</span><span class="sxs-lookup"><span data-stu-id="0a36e-119">was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0a36e-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0a36e-120">0x80041006</span></span> | <span data-ttu-id="0a36e-121">Не хватает памяти доступен для клонирования объекта.</span><span class="sxs-lookup"><span data-stu-id="0a36e-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0a36e-122">0</span><span class="sxs-lookup"><span data-stu-id="0a36e-122">0</span></span> | <span data-ttu-id="0a36e-123">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="0a36e-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0a36e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a36e-124">Remarks</span></span>

<span data-ttu-id="0a36e-125">Эта функция создает оболочку для вызова [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) метод.</span><span class="sxs-lookup"><span data-stu-id="0a36e-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="0a36e-126">Клонированный объект является COM-объект, имеющий значение счетчика ссылок равно 1.</span><span class="sxs-lookup"><span data-stu-id="0a36e-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a36e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0a36e-127">Requirements</span></span>  
 <span data-ttu-id="0a36e-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a36e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a36e-129">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0a36e-129">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="0a36e-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0a36e-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a36e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0a36e-131">See also</span></span>

- [<span data-ttu-id="0a36e-132">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="0a36e-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
