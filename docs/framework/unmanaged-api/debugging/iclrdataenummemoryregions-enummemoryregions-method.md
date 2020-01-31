---
title: Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785640"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="b5369-102">Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="b5369-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="b5369-103">Перечисляет указанные области памяти.</span><span class="sxs-lookup"><span data-stu-id="b5369-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5369-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5369-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5369-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5369-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="b5369-106">окне Указатель на экземпляр [иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md) , вызываемый этим методом для каждой области памяти, перечисленной для уведомления отладчика о результатах.</span><span class="sxs-lookup"><span data-stu-id="b5369-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="b5369-107">Перечисление областей памяти продолжится, даже если обратный вызов указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="b5369-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="b5369-108">окне Не используется.</span><span class="sxs-lookup"><span data-stu-id="b5369-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="b5369-109">окне Значение перечисления [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) , указывающее области памяти для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b5369-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5369-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="b5369-110">Remarks</span></span>  
 <span data-ttu-id="b5369-111">Этот метод использует указанный экземпляр [иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md) для уведомления вызывающего объекта о результатах.</span><span class="sxs-lookup"><span data-stu-id="b5369-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5369-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b5369-112">Requirements</span></span>  
 <span data-ttu-id="b5369-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5369-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5369-114">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="b5369-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b5369-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5369-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5369-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5369-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5369-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5369-117">See also</span></span>

- [<span data-ttu-id="b5369-118">Интерфейс ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="b5369-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
