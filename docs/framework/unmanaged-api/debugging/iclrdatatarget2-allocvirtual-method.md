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
ms.openlocfilehash: 51c06a7f8ea22fc73236131954781d8755274041
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789091"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="2c590-102">Метод ICLRDataTarget2::AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="2c590-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="2c590-103">Вызывается службами доступа к данным среды CLR для выделения памяти в адресном пространстве этого целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="2c590-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c590-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c590-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c590-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c590-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="2c590-106">окне Значение `CLRDATA_ADDRESS`, указывающее запрошенный начальный адрес выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="2c590-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="2c590-107">окне Размер выделяемой памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="2c590-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="2c590-108">окне Флаги, управляющие выделением памяти.</span><span class="sxs-lookup"><span data-stu-id="2c590-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="2c590-109">См. функцию Win32 `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="2c590-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="2c590-110">окне Атрибуты защиты для выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="2c590-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="2c590-111">См. функцию Win32 `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="2c590-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="2c590-112">заполняет Указатель на `CLRDATA_ADDRESS` значение, указывающее фактический начальный адрес выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="2c590-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c590-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="2c590-113">Remarks</span></span>  
 <span data-ttu-id="2c590-114">`AllocVirtual` метод служит логической оболочкой для функции Win32 `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="2c590-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="2c590-115">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="2c590-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c590-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2c590-116">Requirements</span></span>  
 <span data-ttu-id="2c590-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c590-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c590-118">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="2c590-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2c590-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c590-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c590-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c590-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c590-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c590-121">See also</span></span>

- [<span data-ttu-id="2c590-122">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="2c590-122">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="2c590-123">Метод FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="2c590-123">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)
