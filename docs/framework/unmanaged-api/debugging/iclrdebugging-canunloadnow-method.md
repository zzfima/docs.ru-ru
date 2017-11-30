---
title: "Метод ICLRDebugging::CanUnloadNow"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.CanUnloadNow Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b013231666ca6dfde5ab16e58023da1ae2a72941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="e2726-102">Метод ICLRDebugging::CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="e2726-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="e2726-103">Определяет, используется ли библиотека, предоставленный компанией [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейса по-прежнему используется или может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="e2726-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2726-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2726-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2726-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2726-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="e2726-106">[in] Базовый адрес модуля в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="e2726-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2726-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2726-107">Return Value</span></span>  
 <span data-ttu-id="e2726-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e2726-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e2726-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2726-109">HRESULT</span></span>|<span data-ttu-id="e2726-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e2726-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2726-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2726-111">S_OK</span></span>|<span data-ttu-id="e2726-112">Модуль, на который ссылается `hmodule` может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="e2726-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="e2726-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e2726-113">S_FALSE</span></span>|<span data-ttu-id="e2726-114">Модуль, на который ссылается `hmodule` все еще используется.</span><span class="sxs-lookup"><span data-stu-id="e2726-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="e2726-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="e2726-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="e2726-116">Указанный модуль не является модулем CLR.</span><span class="sxs-lookup"><span data-stu-id="e2726-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e2726-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="e2726-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2726-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2726-118">Remarks</span></span>  
 <span data-ttu-id="e2726-119">Этот метод проверяет все экземпляры `ICorDebug*` интерфейсы были выпущены и ни один поток не находится внутри вызова [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="e2726-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2726-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e2726-120">Requirements</span></span>  
 <span data-ttu-id="e2726-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2726-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2726-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2726-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2726-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2726-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2726-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2726-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2726-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e2726-125">See Also</span></span>  
 [<span data-ttu-id="e2726-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e2726-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e2726-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="e2726-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
