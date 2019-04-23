---
title: Метод ICLRDataTarget2::AllocVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ba9200419d6b6fef467ae02bd74101414e125da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091724"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="9840e-102">Метод ICLRDataTarget2::AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="9840e-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="9840e-103">Вызывается службами доступа к данным среды выполнения (CLR) для выделения памяти в адресном пространстве данного целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="9840e-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9840e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9840e-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9840e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9840e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="9840e-106">[in] Объект `CLRDATA_ADDRESS` значение, указывающее запрошенный начальный адрес в памяти для выделения.</span><span class="sxs-lookup"><span data-stu-id="9840e-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="9840e-107">[in] Размер в байтах, выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="9840e-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="9840e-108">[in] Флаги, которые управляют распределением памяти.</span><span class="sxs-lookup"><span data-stu-id="9840e-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="9840e-109">См. в разделе Win32 `VirtualAlloc` функции.</span><span class="sxs-lookup"><span data-stu-id="9840e-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="9840e-110">[in] Атрибуты защиты выделенную память.</span><span class="sxs-lookup"><span data-stu-id="9840e-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="9840e-111">См. в разделе Win32 `VirtualAlloc` функции.</span><span class="sxs-lookup"><span data-stu-id="9840e-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="9840e-112">[out] Указатель на `CLRDATA_ADDRESS` значение, указывающее фактический начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="9840e-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9840e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="9840e-113">Remarks</span></span>  
 <span data-ttu-id="9840e-114">`AllocVirtual` Метод служит в качестве логической программой-оболочкой для Win32 `VirtualAlloc` функции.</span><span class="sxs-lookup"><span data-stu-id="9840e-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="9840e-115">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="9840e-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9840e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9840e-116">Requirements</span></span>  
 <span data-ttu-id="9840e-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9840e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9840e-118">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="9840e-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9840e-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9840e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9840e-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9840e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9840e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9840e-121">See also</span></span>

- [<span data-ttu-id="9840e-122">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="9840e-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="9840e-123">Метод FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="9840e-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
