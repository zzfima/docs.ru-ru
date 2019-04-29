---
title: Функция GetCurrentApartmentType (Справочник по неуправляемым API)
description: Функция GetCurrentApartmentType извлекает тип апартамента, в котором выполняется вызывающий объект.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ead1c1a91b910e7cfbb09f17ba823fc7a77ce0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609013"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="d1a30-103">Функция GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="d1a30-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="d1a30-104">Получает тип подразделения, в котором выполняется вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="d1a30-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d1a30-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1a30-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="d1a30-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1a30-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d1a30-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="d1a30-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d1a30-108">[in] Указатель на [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d1a30-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="d1a30-109">[out] Указатель на [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) значение перечисления, указывающее подразделения вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="d1a30-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="d1a30-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d1a30-110">Return value</span></span>

|<span data-ttu-id="d1a30-111">Константа</span><span class="sxs-lookup"><span data-stu-id="d1a30-111">Constant</span></span>  |<span data-ttu-id="d1a30-112">Значение</span><span class="sxs-lookup"><span data-stu-id="d1a30-112">Value</span></span>  |<span data-ttu-id="d1a30-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d1a30-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="d1a30-114">0</span><span class="sxs-lookup"><span data-stu-id="d1a30-114">0</span></span> | <span data-ttu-id="d1a30-115">Функция успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="d1a30-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="d1a30-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="d1a30-116">0x80000008</span></span> | <span data-ttu-id="d1a30-117">Вызывающий объект не выполняется в подразделении.</span><span class="sxs-lookup"><span data-stu-id="d1a30-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="d1a30-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1a30-118">Remarks</span></span>

<span data-ttu-id="d1a30-119">Эта функция создает оболочку для вызова [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) метод.</span><span class="sxs-lookup"><span data-stu-id="d1a30-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1a30-120">Требования</span><span class="sxs-lookup"><span data-stu-id="d1a30-120">Requirements</span></span>  
 <span data-ttu-id="d1a30-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1a30-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1a30-122">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d1a30-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d1a30-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a30-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a30-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d1a30-124">See also</span></span>

- [<span data-ttu-id="d1a30-125">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="d1a30-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
