---
title: Функция GetCurrentApartmentType (Неуправляемая ссылка на API)
description: Функция GetCurrentApartmentType получает тип квартиры, в которой выполнит абонент.
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
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176829"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="3e952-103">Функция GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="3e952-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="3e952-104">Получает тип подразделения, в котором выполняется вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="3e952-104">Retrieves the type of apartment in which the caller is executing.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3e952-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e952-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a><span data-ttu-id="3e952-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e952-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3e952-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="3e952-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3e952-108">(в) Указатель на экземпляр [IComThreadingInfo.](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)</span><span class="sxs-lookup"><span data-stu-id="3e952-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="3e952-109">(ваут) Указатель на значение перечисления [APTTYPE,](/windows/win32/api/objidlbase/ne-objidlbase-apttype) которое указывает на квартиру вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="3e952-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="3e952-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e952-110">Return value</span></span>

|<span data-ttu-id="3e952-111">Постоянно</span><span class="sxs-lookup"><span data-stu-id="3e952-111">Constant</span></span>  |<span data-ttu-id="3e952-112">Значение</span><span class="sxs-lookup"><span data-stu-id="3e952-112">Value</span></span>  |<span data-ttu-id="3e952-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3e952-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="3e952-114">0</span><span class="sxs-lookup"><span data-stu-id="3e952-114">0</span></span> | <span data-ttu-id="3e952-115">Функция успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="3e952-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="3e952-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="3e952-116">0x80000008</span></span> | <span data-ttu-id="3e952-117">Звонивший не вырвет в квартире.</span><span class="sxs-lookup"><span data-stu-id="3e952-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3e952-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e952-118">Remarks</span></span>

<span data-ttu-id="3e952-119">Эта функция завершает вызов методом [IComThreadingInfo::GetCurrentApartmentType.](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)</span><span class="sxs-lookup"><span data-stu-id="3e952-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e952-120">Требования</span><span class="sxs-lookup"><span data-stu-id="3e952-120">Requirements</span></span>  
 <span data-ttu-id="3e952-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e952-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e952-122">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3e952-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3e952-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e952-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e952-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e952-124">See also</span></span>

- [<span data-ttu-id="3e952-125">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="3e952-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
