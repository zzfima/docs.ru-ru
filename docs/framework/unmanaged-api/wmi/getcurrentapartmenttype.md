---
title: Функция GetCurrentApartmentType (Справочник по неуправляемым API)
description: Функция GetCurrentApartmentType извлекает тип подразделения, в котором выполняется вызывающего объекта.
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
ms.openlocfilehash: ca7b5fa5bf6d845d542d3e80c0571e59f3d4c1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461728"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="2ea56-103">Функция GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="2ea56-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="2ea56-104">Возвращает тип подразделения, в котором выполняется вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="2ea56-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2ea56-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ea56-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="2ea56-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ea56-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2ea56-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="2ea56-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2ea56-108">[in] Указатель на [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2ea56-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="2ea56-109">[out] Указатель на [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) значение перечисления, указывающее подразделению вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="2ea56-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="2ea56-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2ea56-110">Return value</span></span>


|<span data-ttu-id="2ea56-111">Константа</span><span class="sxs-lookup"><span data-stu-id="2ea56-111">Constant</span></span>  |<span data-ttu-id="2ea56-112">Значение</span><span class="sxs-lookup"><span data-stu-id="2ea56-112">Value</span></span>  |<span data-ttu-id="2ea56-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2ea56-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="2ea56-114">0</span><span class="sxs-lookup"><span data-stu-id="2ea56-114">0</span></span> | <span data-ttu-id="2ea56-115">Выполнение функции было завершено успешно.</span><span class="sxs-lookup"><span data-stu-id="2ea56-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="2ea56-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="2ea56-116">0x80000008</span></span> | <span data-ttu-id="2ea56-117">Вызывающий объект не выполняется в подразделении.</span><span class="sxs-lookup"><span data-stu-id="2ea56-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="2ea56-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ea56-118">Remarks</span></span>

<span data-ttu-id="2ea56-119">Эта функция создает оболочку для вызова [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="2ea56-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2ea56-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2ea56-120">Requirements</span></span>  
 <span data-ttu-id="2ea56-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ea56-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ea56-122">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2ea56-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2ea56-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2ea56-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea56-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2ea56-124">See also</span></span>  
[<span data-ttu-id="2ea56-125">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2ea56-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
