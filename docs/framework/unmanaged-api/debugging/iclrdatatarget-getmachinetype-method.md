---
title: Метод ICLRDataTarget::GetMachineType
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff9c88d534e0bfe51075a76581af37aba791a3da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148477"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="2ba35-102">Метод ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="2ba35-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="2ba35-103">Получает идентификатор для типа набора инструкций, целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="2ba35-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ba35-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ba35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ba35-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="2ba35-106">[out] Использует указатель на значение, указывающее набора инструкций, в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="2ba35-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="2ba35-107">Возвращенный `machineType` является одной из констант IMAGE_FILE_MACHINE, которые определены в файле заголовка WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="2ba35-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba35-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2ba35-108">Requirements</span></span>  
 <span data-ttu-id="2ba35-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ba35-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba35-110">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2ba35-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2ba35-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ba35-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ba35-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba35-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba35-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2ba35-113">See also</span></span>

- [<span data-ttu-id="2ba35-114">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="2ba35-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
