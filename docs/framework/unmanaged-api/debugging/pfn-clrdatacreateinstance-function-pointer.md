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
ms.openlocfilehash: 433f34447d3bd1a57ca1e289cb0eab3facac2c69
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790360"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="421ac-102">Указатель функции PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="421ac-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="421ac-103">Указывает на функцию, которая создает объект интерфейса для указанного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="421ac-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="421ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="421ac-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="421ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="421ac-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="421ac-106">окне Идентификатор интерфейса, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="421ac-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="421ac-107">окне Указатель на реализуемый пользователем объект [ICLRDataTarget](iclrdatatarget-interface.md) , представляющий целевой элемент, для которого создается объект интерфейса.</span><span class="sxs-lookup"><span data-stu-id="421ac-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="421ac-108">заполняет Указатель на адрес возвращенного объекта интерфейса.</span><span class="sxs-lookup"><span data-stu-id="421ac-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="421ac-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="421ac-109">Remarks</span></span>  
 <span data-ttu-id="421ac-110">Объект `ICLRDataTarget` реализуется модулем записи приложения отладки.</span><span class="sxs-lookup"><span data-stu-id="421ac-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="421ac-111">Реализация зависит от типа представляемого целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="421ac-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="421ac-112">Целевой элемент может быть процессом, дампом памяти, удаленным компьютером и т. д.</span><span class="sxs-lookup"><span data-stu-id="421ac-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421ac-113">Требования</span><span class="sxs-lookup"><span data-stu-id="421ac-113">Requirements</span></span>  
 <span data-ttu-id="421ac-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421ac-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421ac-115">**Заголовок:** Клрдата. idl</span><span class="sxs-lookup"><span data-stu-id="421ac-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="421ac-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="421ac-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="421ac-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421ac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421ac-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="421ac-118">See also</span></span>

- [<span data-ttu-id="421ac-119">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="421ac-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
