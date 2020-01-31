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
ms.openlocfilehash: 7eda9bfff6de6b386c16ad0a188931d9d3adcb93
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793658"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="80423-102">Метод ICLRDataTarget2::FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="80423-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="80423-103">Вызывается службами доступа к данным среды CLR для освобождения памяти, которая была ранее выделена в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="80423-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80423-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80423-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80423-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80423-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="80423-106">окне Значение `CLRDATA_ADDRESS`, указывающее начальный адрес памяти для высвобождения.</span><span class="sxs-lookup"><span data-stu-id="80423-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="80423-107">окне Размер (в байтах) памяти, которая должна быть освобождена.</span><span class="sxs-lookup"><span data-stu-id="80423-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="80423-108">окне Флаги, управляющие освобождением памяти.</span><span class="sxs-lookup"><span data-stu-id="80423-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="80423-109">См. функцию Win32 `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="80423-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80423-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="80423-110">Remarks</span></span>  
 <span data-ttu-id="80423-111">`FreeVirtual` метод служит логической оболочкой для функции Win32 `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="80423-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="80423-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="80423-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80423-113">Требования</span><span class="sxs-lookup"><span data-stu-id="80423-113">Requirements</span></span>  
 <span data-ttu-id="80423-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80423-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80423-115">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="80423-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="80423-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80423-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80423-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80423-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80423-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="80423-118">See also</span></span>

- [<span data-ttu-id="80423-119">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="80423-119">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="80423-120">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="80423-120">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
