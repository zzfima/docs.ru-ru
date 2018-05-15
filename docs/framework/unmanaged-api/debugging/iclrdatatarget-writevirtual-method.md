---
title: Метод ICLRDataTarget::WriteVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e55bc18c7a41e235d1ba6274067c45c26dc7262a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="e3205-102">Метод ICLRDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="e3205-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="e3205-103">Записывает данные из указанного буфера указанного адреса виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="e3205-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3205-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3205-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3205-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3205-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="e3205-106">[in] CLRDATA_ADDRESS, в которой хранятся адресов виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="e3205-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e3205-107">[in] Указатель на буфер, в которой хранятся данные, которые требуется записать.</span><span class="sxs-lookup"><span data-stu-id="e3205-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="e3205-108">[in] Число байтов для записи.</span><span class="sxs-lookup"><span data-stu-id="e3205-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="e3205-109">[out] Указатель на фактическое число байтов, которые были записаны.</span><span class="sxs-lookup"><span data-stu-id="e3205-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3205-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e3205-110">Requirements</span></span>  
 <span data-ttu-id="e3205-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3205-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3205-112">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e3205-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e3205-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3205-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3205-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3205-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3205-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e3205-115">See Also</span></span>  
 [<span data-ttu-id="e3205-116">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="e3205-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
