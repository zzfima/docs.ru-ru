---
title: "Метод ICLRDataTarget::SetTLSValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.SetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75c9d25b496e300d66844e3fd88655ab38da4b0e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="3591b-102">Метод ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="3591b-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="3591b-103">Задает значение в локальном хранилище потока (TLS) заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="3591b-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="3591b-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3591b-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3591b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3591b-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3591b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3591b-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3591b-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3591b-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="3591b-108">[in] Индекс расположения.</span><span class="sxs-lookup"><span data-stu-id="3591b-108">[in] The index of the location.</span></span> <span data-ttu-id="3591b-109">Это значение должно быть допустимым индексом в локальном хранилище заданного потока.</span><span class="sxs-lookup"><span data-stu-id="3591b-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="3591b-110">[in] Объект `CLRDATA_ADDRESS` значение, которое указывает значение, помещаемое в заданном расположении TLS.</span><span class="sxs-lookup"><span data-stu-id="3591b-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3591b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3591b-111">Remarks</span></span>  
 <span data-ttu-id="3591b-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="3591b-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3591b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3591b-113">Requirements</span></span>  
 <span data-ttu-id="3591b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3591b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3591b-115">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3591b-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3591b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3591b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3591b-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3591b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3591b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3591b-118">See Also</span></span>  
 [<span data-ttu-id="3591b-119">ICLRDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3591b-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
