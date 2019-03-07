---
title: Метод ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 421fb371094c21948486e56d0881163e7a6961a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465287"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="5e729-102">Метод ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="5e729-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="5e729-103">Задает значение в локальном хранилище потока (TLS) заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="5e729-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="5e729-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5e729-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e729-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e729-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e729-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e729-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="5e729-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5e729-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="5e729-108">[in] Индекс расположения.</span><span class="sxs-lookup"><span data-stu-id="5e729-108">[in] The index of the location.</span></span> <span data-ttu-id="5e729-109">Это значение должно быть допустимым индексом в локальном хранилище из указанного потока.</span><span class="sxs-lookup"><span data-stu-id="5e729-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="5e729-110">[in] Объект `CLRDATA_ADDRESS` значение, указывающее значение, помещаемое в заданном расположении TLS.</span><span class="sxs-lookup"><span data-stu-id="5e729-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e729-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e729-111">Remarks</span></span>  
 <span data-ttu-id="5e729-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="5e729-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e729-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5e729-113">Requirements</span></span>  
 <span data-ttu-id="5e729-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e729-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e729-115">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5e729-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5e729-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e729-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e729-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e729-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e729-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5e729-118">See also</span></span>
- [<span data-ttu-id="5e729-119">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="5e729-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
