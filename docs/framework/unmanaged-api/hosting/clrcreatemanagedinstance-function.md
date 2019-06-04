---
title: Функция ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67bd6e8a0519d35b867cb525d5ff7730c0459016
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490678"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="2bb4a-102">Функция ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="2bb4a-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="2bb4a-103">Создает экземпляра указанного управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="2bb4a-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="2bb4a-105">Использовать COM-компоненты для создания экземпляра управляемого типа или размещение (см. в разделе [CLR размещение интерфейсов, добавленные в .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="2bb4a-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb4a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bb4a-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bb4a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2bb4a-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="2bb4a-108">[in] Указатель на имя запрашиваемого типа экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="2bb4a-109">[in] `IID` Запрашиваемого типа экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="2bb4a-110">[out] Указатель на указатель на экземпляр управляемого типа, который был запрошен вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bb4a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="2bb4a-111">Remarks</span></span>  
 <span data-ttu-id="2bb4a-112">Среда CLR, уже должны быть загружены в процесс.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="2bb4a-113">Например, его можно загрузить с помощью вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функцию перед `ClrCreateManagedInstance` функция вызывается.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="2bb4a-114">Если среда выполнения не загружается, `ClrCreateManagedInstance` сначала пытается загрузить v1.0.3705 среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="2bb4a-115">Если это не удается, предпринимается попытка загрузить последнюю версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2bb4a-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb4a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2bb4a-116">Requirements</span></span>  
 <span data-ttu-id="2bb4a-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bb4a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb4a-118">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2bb4a-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bb4a-119">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bb4a-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bb4a-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb4a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb4a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2bb4a-121">See also</span></span>

- [<span data-ttu-id="2bb4a-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="2bb4a-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="2bb4a-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="2bb4a-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
