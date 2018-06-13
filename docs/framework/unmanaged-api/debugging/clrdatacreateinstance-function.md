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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9d4965751db1a70871270317a644b0acb1302f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405984"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="39c1c-102">Функция CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="39c1c-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="39c1c-103">Создает объект интерфейса для заданного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="39c1c-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39c1c-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39c1c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="39c1c-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="39c1c-106">[in] Идентификатор интерфейса для создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="39c1c-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="39c1c-107">[in] Указатель на реализации пользователя [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , представляющий целевой элемент, для которого необходимо создать объект интерфейса.</span><span class="sxs-lookup"><span data-stu-id="39c1c-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="39c1c-108">[out] Указатель на адрес объекта, возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="39c1c-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39c1c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="39c1c-109">Remarks</span></span>  
 <span data-ttu-id="39c1c-110">`ICLRDataTarget` Объект реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="39c1c-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="39c1c-111">Реализация зависит от типа представляемого целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="39c1c-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="39c1c-112">Конечный элемент может быть процесс, дамп памяти, удаленный компьютер и т. д.</span><span class="sxs-lookup"><span data-stu-id="39c1c-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c1c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="39c1c-113">Requirements</span></span>  
 <span data-ttu-id="39c1c-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c1c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c1c-115">**Заголовок:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="39c1c-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="39c1c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39c1c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39c1c-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c1c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c1c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="39c1c-118">See Also</span></span>  
 [<span data-ttu-id="39c1c-119">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="39c1c-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
