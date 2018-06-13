---
title: Метод ICLRDataTarget::GetPointerSize
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 749ec14af7bffee87afbe5c0705a6ddf68da5fd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406498"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="f8161-102">Метод ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="f8161-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="f8161-103">Возвращает размер в байтах, типа указателя, использующего целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="f8161-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="f8161-104">Этот метод вызывается службами доступа к данным среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f8161-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8161-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8161-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8161-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8161-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="f8161-107">[out] Указатель на целочисленное значение, указывающее размер в байтах для указателя на целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="f8161-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8161-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8161-108">Remarks</span></span>  
 <span data-ttu-id="f8161-109">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="f8161-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8161-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f8161-110">Requirements</span></span>  
 <span data-ttu-id="f8161-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8161-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8161-112">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f8161-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f8161-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8161-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8161-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8161-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8161-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f8161-115">See Also</span></span>  
 [<span data-ttu-id="f8161-116">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f8161-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
