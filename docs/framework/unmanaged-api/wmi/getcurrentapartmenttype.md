---
title: Функция Жеткуррентапартменттипе (Справочник по неуправляемым API)
description: Функция Жеткуррентапартменттипе Извлекает тип подразделения, в котором выполняется вызывающий объект.
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
ms.openlocfilehash: ff64be47802a46979818ab54cc3efb4112dd05e0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798625"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="ffdea-103">Функция Жеткуррентапартменттипе</span><span class="sxs-lookup"><span data-stu-id="ffdea-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="ffdea-104">Получает тип подразделения, в котором выполняется вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="ffdea-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ffdea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffdea-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="ffdea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffdea-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ffdea-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="ffdea-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ffdea-108">окне Указатель на экземпляр [икомсреадингинфо](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) .</span><span class="sxs-lookup"><span data-stu-id="ffdea-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="ffdea-109">заполняет Указатель на значение перечисления [апттипе](/windows/win32/api/objidlbase/ne-objidlbase-apttype) , указывающее подразделение вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="ffdea-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="ffdea-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ffdea-110">Return value</span></span>

|<span data-ttu-id="ffdea-111">Константа</span><span class="sxs-lookup"><span data-stu-id="ffdea-111">Constant</span></span>  |<span data-ttu-id="ffdea-112">Значение</span><span class="sxs-lookup"><span data-stu-id="ffdea-112">Value</span></span>  |<span data-ttu-id="ffdea-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ffdea-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="ffdea-114">0</span><span class="sxs-lookup"><span data-stu-id="ffdea-114">0</span></span> | <span data-ttu-id="ffdea-115">Функция успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="ffdea-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="ffdea-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="ffdea-116">0x80000008</span></span> | <span data-ttu-id="ffdea-117">Вызывающий объект не выполняется в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="ffdea-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ffdea-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="ffdea-118">Remarks</span></span>

<span data-ttu-id="ffdea-119">Эта функция заключает в оболочку вызов метода [икомсреадингинфо:: жеткуррентапартменттипе](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="ffdea-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ffdea-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ffdea-120">Requirements</span></span>  
 <span data-ttu-id="ffdea-121">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffdea-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffdea-122">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ffdea-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ffdea-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ffdea-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdea-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ffdea-124">See also</span></span>

- [<span data-ttu-id="ffdea-125">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="ffdea-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
