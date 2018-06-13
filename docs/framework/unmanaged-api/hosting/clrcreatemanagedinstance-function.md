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
ms.openlocfilehash: a375ea586bacc2d3dafe53d493a7467730fae889
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432325"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="a5024-102">Функция ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="a5024-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="a5024-103">Создает экземпляр указанного управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="a5024-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="a5024-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5024-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="a5024-105">Используйте активации COM для создания экземпляра управляемого типа или размещения (в разделе [CLR размещение интерфейсов, добавленные в платформу .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="a5024-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5024-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5024-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5024-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5024-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="a5024-108">[in] Указатель на имя запрашиваемого типа экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a5024-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="a5024-109">[in] `IID` Запрашиваемого типа экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a5024-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a5024-110">[out] Указатель на указатель на экземпляр управляемого типа, который был запрошен вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="a5024-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5024-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5024-111">Remarks</span></span>  
 <span data-ttu-id="a5024-112">Общеязыковая среда выполнения уже должна быть загружена в процесс.</span><span class="sxs-lookup"><span data-stu-id="a5024-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="a5024-113">Например, его можно загрузить с помощью вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции перед `ClrCreateManagedInstance` функция.</span><span class="sxs-lookup"><span data-stu-id="a5024-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="a5024-114">Если среда выполнения не загружается, `ClrCreateManagedInstance` сначала пытается загрузить v1.0.3705 среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5024-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="a5024-115">В случае неудачи пытается загрузить последнюю версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5024-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5024-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a5024-116">Requirements</span></span>  
 <span data-ttu-id="a5024-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5024-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5024-118">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a5024-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5024-119">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5024-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5024-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5024-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5024-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a5024-121">See Also</span></span>  
 [<span data-ttu-id="a5024-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="a5024-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="a5024-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="a5024-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
