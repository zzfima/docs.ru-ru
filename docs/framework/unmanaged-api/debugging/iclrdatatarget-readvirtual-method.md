---
title: "Метод ICLRDataTarget::ReadVirtual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.ReadVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dffe95b1bab3d8dae72cc62f5d45baa85e39e590
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="88e0d-102">Метод ICLRDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="88e0d-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="88e0d-103">Считывает данные из указанного адреса виртуальной памяти в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="88e0d-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88e0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88e0d-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88e0d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88e0d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="88e0d-106">[in] CLRDATA_ADDRESS, в которой хранятся адресов виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="88e0d-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="88e0d-107">[out] Указатель на буфер, получающий данные.</span><span class="sxs-lookup"><span data-stu-id="88e0d-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="88e0d-108">[in] Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="88e0d-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="88e0d-109">[out] Указатель на число возвращенных байтов.</span><span class="sxs-lookup"><span data-stu-id="88e0d-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88e0d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="88e0d-110">Requirements</span></span>  
 <span data-ttu-id="88e0d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88e0d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88e0d-112">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="88e0d-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="88e0d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88e0d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88e0d-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88e0d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e0d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="88e0d-115">See Also</span></span>  
 [<span data-ttu-id="88e0d-116">ICLRDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="88e0d-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
