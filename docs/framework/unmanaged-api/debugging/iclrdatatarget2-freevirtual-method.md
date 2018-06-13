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
ms.openlocfilehash: e7351dfb046653e4f3e20e0dc8a4bba8653ec36e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404652"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="a51d8-102">Метод ICLRDataTarget2::FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="a51d8-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="a51d8-103">Вызывается службами доступа к данным среды выполнения (CLR) для освобождения памяти, который ранее был выделен в адресное пространство целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="a51d8-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a51d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a51d8-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a51d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a51d8-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="a51d8-106">[in] Объект `CLRDATA_ADDRESS` значение, которое определяет начальный адрес освобождаемой памяти.</span><span class="sxs-lookup"><span data-stu-id="a51d8-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="a51d8-107">[in] Размер в байтах для освобождения памяти.</span><span class="sxs-lookup"><span data-stu-id="a51d8-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="a51d8-108">[in] Флаги, управляющие освобождении памяти.</span><span class="sxs-lookup"><span data-stu-id="a51d8-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="a51d8-109">В разделе Win32 `VirtualFree` функции.</span><span class="sxs-lookup"><span data-stu-id="a51d8-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a51d8-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a51d8-110">Remarks</span></span>  
 <span data-ttu-id="a51d8-111">`FreeVirtual` Метод служит логической программой-оболочкой для функции Win32 `VirtualFree` функции.</span><span class="sxs-lookup"><span data-stu-id="a51d8-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="a51d8-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="a51d8-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a51d8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a51d8-113">Requirements</span></span>  
 <span data-ttu-id="a51d8-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a51d8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a51d8-115">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="a51d8-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a51d8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a51d8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a51d8-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a51d8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51d8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a51d8-118">See Also</span></span>  
 [<span data-ttu-id="a51d8-119">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a51d8-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="a51d8-120">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="a51d8-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
