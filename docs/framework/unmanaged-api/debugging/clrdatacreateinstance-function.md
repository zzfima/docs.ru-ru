---
title: Функция CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179365"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="c9a72-102">Функция CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="c9a72-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="c9a72-103">Создает объект интерфейса для указанного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="c9a72-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9a72-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9a72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9a72-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="c9a72-106">(в) Идентификатор интерфейса, который должен быть мгновенно.</span><span class="sxs-lookup"><span data-stu-id="c9a72-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="c9a72-107">(в) Указатель на реализованный пользователем объект [ICLRDataTarget,](iclrdatatarget-interface.md) представляющий целевой элемент для создания объекта интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c9a72-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="c9a72-108">(ваут) Указатель на адрес возвращенного объекта интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c9a72-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9a72-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9a72-109">Remarks</span></span>  
 <span data-ttu-id="c9a72-110">Объект `ICLRDataTarget` реализован автором приложения отладки.</span><span class="sxs-lookup"><span data-stu-id="c9a72-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="c9a72-111">Реализация зависит от типа представленного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="c9a72-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="c9a72-112">Целевой элемент может быть процесс, свалка памяти, удаленной машины, и так далее.</span><span class="sxs-lookup"><span data-stu-id="c9a72-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9a72-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c9a72-113">Requirements</span></span>  
 <span data-ttu-id="c9a72-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9a72-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9a72-115">**Заголовок:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="c9a72-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="c9a72-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9a72-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9a72-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9a72-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a72-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c9a72-118">See also</span></span>

- [<span data-ttu-id="c9a72-119">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="c9a72-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
