---
title: Метод ICLRDataTarget2::FreeVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b30bd3e97af8d222f629c5b4f9f318a9b6379e78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697963"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="526d9-102">Метод ICLRDataTarget2::FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="526d9-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="526d9-103">Вызывается службами доступа к данным среды выполнения (CLR) для освобождения памяти, который ранее был выделен в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="526d9-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="526d9-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="526d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="526d9-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="526d9-106">[in] Объект `CLRDATA_ADDRESS` значение, указывающее начальный адрес освобождаемой памяти.</span><span class="sxs-lookup"><span data-stu-id="526d9-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="526d9-107">[in] Размер в байтах освобождаемой памяти.</span><span class="sxs-lookup"><span data-stu-id="526d9-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="526d9-108">[in] Флаги, управляющие освобождение памяти.</span><span class="sxs-lookup"><span data-stu-id="526d9-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="526d9-109">См. в разделе Win32 `VirtualFree` функции.</span><span class="sxs-lookup"><span data-stu-id="526d9-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="526d9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="526d9-110">Remarks</span></span>  
 <span data-ttu-id="526d9-111">`FreeVirtual` Метод служит в качестве логической программой-оболочкой для Win32 `VirtualFree` функции.</span><span class="sxs-lookup"><span data-stu-id="526d9-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="526d9-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="526d9-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="526d9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="526d9-113">Requirements</span></span>  
 <span data-ttu-id="526d9-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="526d9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="526d9-115">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="526d9-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="526d9-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="526d9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="526d9-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="526d9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526d9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="526d9-118">See also</span></span>

- [<span data-ttu-id="526d9-119">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="526d9-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="526d9-120">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="526d9-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
