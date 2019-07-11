---
title: Метод ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65ac05a524297029ca50970bdd231c6a9112e35c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748396"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="506a8-102">Метод ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="506a8-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="506a8-103">Загружает библиотеку .NET Framework из общеязыковой среды выполнения (CLR), представленный [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="506a8-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="506a8-104">Этот метод заменяет [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="506a8-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="506a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="506a8-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="506a8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="506a8-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="506a8-107">[in] Имя сборки для загрузки.</span><span class="sxs-lookup"><span data-stu-id="506a8-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="506a8-108">[out] Дескриптор загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="506a8-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="506a8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="506a8-109">Return Value</span></span>  
 <span data-ttu-id="506a8-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="506a8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="506a8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="506a8-111">HRESULT</span></span>|<span data-ttu-id="506a8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="506a8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="506a8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="506a8-113">S_OK</span></span>|<span data-ttu-id="506a8-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="506a8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="506a8-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="506a8-115">E_POINTER</span></span>|<span data-ttu-id="506a8-116">`pwzDllName` или `phndModule` равно null.</span><span class="sxs-lookup"><span data-stu-id="506a8-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="506a8-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="506a8-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="506a8-118">Недостаточно памяти для обработки запроса.</span><span class="sxs-lookup"><span data-stu-id="506a8-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="506a8-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="506a8-119">Remarks</span></span>  
 <span data-ttu-id="506a8-120">Этот метод загружает только библиотеки DLL, включенные в распространяемый пакет .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="506a8-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="506a8-121">Он не может загружать сборки, созданное пользователем.</span><span class="sxs-lookup"><span data-stu-id="506a8-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="506a8-122">Требования</span><span class="sxs-lookup"><span data-stu-id="506a8-122">Requirements</span></span>  
 <span data-ttu-id="506a8-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="506a8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="506a8-124">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="506a8-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="506a8-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="506a8-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="506a8-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506a8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506a8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="506a8-127">See also</span></span>

- [<span data-ttu-id="506a8-128">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="506a8-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="506a8-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="506a8-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="506a8-130">Размещение</span><span class="sxs-lookup"><span data-stu-id="506a8-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
