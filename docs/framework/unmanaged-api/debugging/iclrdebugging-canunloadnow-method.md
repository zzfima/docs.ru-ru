---
title: Метод ICLRDebugging::CanUnloadNow
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80559ef685a2dbf48d65e0d81432a5edbd5528bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072874"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="b2176-102">Метод ICLRDebugging::CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="b2176-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="b2176-103">Определяет, является ли библиотеку, предоставленным [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейс по-прежнему используется, или может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="b2176-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2176-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2176-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2176-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2176-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="b2176-106">[in] Базовый адрес модуля в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="b2176-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2176-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2176-107">Return Value</span></span>  
 <span data-ttu-id="b2176-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b2176-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b2176-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2176-109">HRESULT</span></span>|<span data-ttu-id="b2176-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b2176-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2176-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2176-111">S_OK</span></span>|<span data-ttu-id="b2176-112">Модуль, на который ссылается `hmodule` может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="b2176-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="b2176-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b2176-113">S_FALSE</span></span>|<span data-ttu-id="b2176-114">Модуль, на который ссылается `hmodule` по-прежнему используется.</span><span class="sxs-lookup"><span data-stu-id="b2176-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="b2176-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="b2176-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="b2176-116">Указанный модуль не является модулем CLR.</span><span class="sxs-lookup"><span data-stu-id="b2176-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b2176-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="b2176-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2176-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2176-118">Remarks</span></span>  
 <span data-ttu-id="b2176-119">Этот метод проверяет все экземпляры `ICorDebug*` интерфейсы были выпущены и ни один поток не находится внутри вызова [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b2176-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2176-120">Требования</span><span class="sxs-lookup"><span data-stu-id="b2176-120">Requirements</span></span>  
 <span data-ttu-id="b2176-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2176-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2176-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2176-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2176-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2176-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2176-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2176-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2176-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b2176-125">See also</span></span>

- [<span data-ttu-id="b2176-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b2176-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b2176-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="b2176-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
