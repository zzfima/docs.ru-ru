---
title: "Метод ICLRDataTarget2::FreeVirtual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.FreeVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1619e9eb02eec1985c3c550626ef955162d1b984
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="cd652-102">Метод ICLRDataTarget2::FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="cd652-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="cd652-103">Вызывается службами доступа к данным среды выполнения (CLR) для освобождения памяти, который ранее был выделен в адресное пространство целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="cd652-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd652-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd652-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd652-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd652-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="cd652-106">[in] Объект `CLRDATA_ADDRESS` значение, которое определяет начальный адрес освобождаемой памяти.</span><span class="sxs-lookup"><span data-stu-id="cd652-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="cd652-107">[in] Размер в байтах для освобождения памяти.</span><span class="sxs-lookup"><span data-stu-id="cd652-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="cd652-108">[in] Флаги, управляющие освобождении памяти.</span><span class="sxs-lookup"><span data-stu-id="cd652-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="cd652-109">В разделе Win32 `VirtualFree` функции.</span><span class="sxs-lookup"><span data-stu-id="cd652-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd652-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd652-110">Remarks</span></span>  
 <span data-ttu-id="cd652-111">`FreeVirtual` Метод служит логической программой-оболочкой для функции Win32 `VirtualFree` функции.</span><span class="sxs-lookup"><span data-stu-id="cd652-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="cd652-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="cd652-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd652-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cd652-113">Requirements</span></span>  
 <span data-ttu-id="cd652-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd652-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd652-115">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="cd652-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cd652-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd652-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd652-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd652-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd652-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cd652-118">See Also</span></span>  
 [<span data-ttu-id="cd652-119">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="cd652-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="cd652-120">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="cd652-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
