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
ms.openlocfilehash: 7a274aaec4919b86f32f98e4d8278dc12748fb2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785481"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="86e4a-102">Метод ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="86e4a-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="86e4a-103">Возвращает размер (в байтах) типа указателя, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="86e4a-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="86e4a-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="86e4a-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e4a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86e4a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86e4a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="86e4a-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="86e4a-107">заполняет Указатель на целочисленное значение, указывающее размер (в байтах) указателя на целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="86e4a-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86e4a-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="86e4a-108">Remarks</span></span>  
 <span data-ttu-id="86e4a-109">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="86e4a-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e4a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="86e4a-110">Requirements</span></span>  
 <span data-ttu-id="86e4a-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e4a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e4a-112">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="86e4a-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="86e4a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86e4a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86e4a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e4a-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="86e4a-115">See also</span></span>

- [<span data-ttu-id="86e4a-116">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="86e4a-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
