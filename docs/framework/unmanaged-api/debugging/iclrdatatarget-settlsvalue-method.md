---
title: Метод ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 6e6e157c7176a0f4f1ad3c585977e2cfb31c33d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793689"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="12169-102">Метод ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="12169-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="12169-103">Задает значение в локальном хранилище потока (TLS) указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="12169-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="12169-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="12169-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12169-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12169-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12169-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="12169-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="12169-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="12169-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="12169-108">окне Индекс расположения.</span><span class="sxs-lookup"><span data-stu-id="12169-108">[in] The index of the location.</span></span> <span data-ttu-id="12169-109">Это значение должно быть допустимым индексом в локальном хранилище указанного потока.</span><span class="sxs-lookup"><span data-stu-id="12169-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="12169-110">окне Значение `CLRDATA_ADDRESS`, указывающее значение, помещаемое в заданное расположение TLS.</span><span class="sxs-lookup"><span data-stu-id="12169-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12169-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="12169-111">Remarks</span></span>  
 <span data-ttu-id="12169-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="12169-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12169-113">Требования</span><span class="sxs-lookup"><span data-stu-id="12169-113">Requirements</span></span>  
 <span data-ttu-id="12169-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12169-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12169-115">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="12169-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="12169-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12169-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12169-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12169-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12169-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="12169-118">See also</span></span>

- [<span data-ttu-id="12169-119">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="12169-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
