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
ms.openlocfilehash: 8a999dc1850a41612f8896ff9a7ed96cd8c3a2fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509139"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="150ef-103">Функция GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="150ef-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="150ef-104">Получает тип подразделения, в котором выполняется вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="150ef-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="150ef-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="150ef-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="150ef-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="150ef-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="150ef-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="150ef-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="150ef-108">[in] Указатель на [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="150ef-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="150ef-109">[out] Указатель на [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) значение перечисления, указывающее подразделения вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="150ef-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="150ef-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="150ef-110">Return value</span></span>


|<span data-ttu-id="150ef-111">Константа</span><span class="sxs-lookup"><span data-stu-id="150ef-111">Constant</span></span>  |<span data-ttu-id="150ef-112">Значение</span><span class="sxs-lookup"><span data-stu-id="150ef-112">Value</span></span>  |<span data-ttu-id="150ef-113">Описание</span><span class="sxs-lookup"><span data-stu-id="150ef-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="150ef-114">0</span><span class="sxs-lookup"><span data-stu-id="150ef-114">0</span></span> | <span data-ttu-id="150ef-115">Функция успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="150ef-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="150ef-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="150ef-116">0x80000008</span></span> | <span data-ttu-id="150ef-117">Вызывающий объект не выполняется в подразделении.</span><span class="sxs-lookup"><span data-stu-id="150ef-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="150ef-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="150ef-118">Remarks</span></span>

<span data-ttu-id="150ef-119">Эта функция создает оболочку для вызова [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) метод.</span><span class="sxs-lookup"><span data-stu-id="150ef-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="150ef-120">Требования</span><span class="sxs-lookup"><span data-stu-id="150ef-120">Requirements</span></span>  
 <span data-ttu-id="150ef-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="150ef-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="150ef-122">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="150ef-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="150ef-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="150ef-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150ef-124">См. также</span><span class="sxs-lookup"><span data-stu-id="150ef-124">See also</span></span>
- [<span data-ttu-id="150ef-125">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="150ef-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
