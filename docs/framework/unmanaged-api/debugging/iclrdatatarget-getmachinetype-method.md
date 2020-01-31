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
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793743"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="44ccd-102">Метод ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="44ccd-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="44ccd-103">Возвращает идентификатор для типа набора инструкций, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="44ccd-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ccd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44ccd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44ccd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44ccd-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="44ccd-106">заполняет Указатель на значение, указывающее набор инструкций, который используется целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="44ccd-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="44ccd-107">Возвращаемый `machineType` является одной из IMAGE_FILE_MACHINE констант, которые определены в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="44ccd-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44ccd-108">Требования</span><span class="sxs-lookup"><span data-stu-id="44ccd-108">Requirements</span></span>  
 <span data-ttu-id="44ccd-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44ccd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44ccd-110">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="44ccd-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="44ccd-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44ccd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44ccd-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44ccd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ccd-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="44ccd-113">See also</span></span>

- [<span data-ttu-id="44ccd-114">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="44ccd-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
