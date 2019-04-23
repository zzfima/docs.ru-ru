---
title: Указатель функции PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff2ddb1e98f3455c6915acf8149f528176228425
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177987"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="1f3fe-102">Указатель функции PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="1f3fe-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="1f3fe-103">Указывает на функцию, которая создает объект интерфейса для заданного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f3fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f3fe-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f3fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f3fe-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="1f3fe-106">[in] Идентификатор интерфейса для создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="1f3fe-107">[in] Указатель на реализуется пользователем [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , представляющий целевой элемент, для которого создается объект интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="1f3fe-108">[out] Указатель на адрес объекта возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f3fe-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f3fe-109">Remarks</span></span>  
 <span data-ttu-id="1f3fe-110">`ICLRDataTarget` Объект реализуется разработчиком отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="1f3fe-111">Реализация зависит от тип представляемого целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="1f3fe-112">Конечный элемент может быть процесс, дамп памяти, удаленный компьютер и т. д.</span><span class="sxs-lookup"><span data-stu-id="1f3fe-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f3fe-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1f3fe-113">Requirements</span></span>  
 <span data-ttu-id="1f3fe-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f3fe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f3fe-115">**Заголовок.** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="1f3fe-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="1f3fe-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f3fe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f3fe-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f3fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3fe-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1f3fe-118">See also</span></span>

- [<span data-ttu-id="1f3fe-119">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="1f3fe-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
