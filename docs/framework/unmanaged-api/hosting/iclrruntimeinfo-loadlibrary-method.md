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
ms.openlocfilehash: 3fe1f93c621fd567471b9a49e4aa75cb90e6e0e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161165"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="1a0b3-102">Метод ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="1a0b3-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="1a0b3-103">Загружает библиотеку .NET Framework из общеязыковой среды выполнения (CLR), представленный [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="1a0b3-104">Этот метод заменяет [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a0b3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a0b3-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a0b3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a0b3-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="1a0b3-107">[in] Имя сборки для загрузки.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="1a0b3-108">[out] Дескриптор загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a0b3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a0b3-109">Return Value</span></span>  
 <span data-ttu-id="1a0b3-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1a0b3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a0b3-111">HRESULT</span></span>|<span data-ttu-id="1a0b3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1a0b3-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a0b3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a0b3-113">S_OK</span></span>|<span data-ttu-id="1a0b3-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1a0b3-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1a0b3-115">E_POINTER</span></span>|`pwzDllName` <span data-ttu-id="1a0b3-116">или `phndModule` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-116">or `phndModule` is null.</span></span>|  
|<span data-ttu-id="1a0b3-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1a0b3-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1a0b3-118">Недостаточно памяти для обработки запроса.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a0b3-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a0b3-119">Remarks</span></span>  
 <span data-ttu-id="1a0b3-120">Этот метод загружает только библиотеки DLL, включенные в распространяемый пакет .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="1a0b3-121">Он не может загружать сборки, созданное пользователем.</span><span class="sxs-lookup"><span data-stu-id="1a0b3-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a0b3-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1a0b3-122">Requirements</span></span>  
 <span data-ttu-id="1a0b3-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a0b3-124">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1a0b3-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1a0b3-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a0b3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1a0b3-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1a0b3-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a0b3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1a0b3-127">See also</span></span>

- [<span data-ttu-id="1a0b3-128">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="1a0b3-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1a0b3-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1a0b3-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1a0b3-130">Размещение</span><span class="sxs-lookup"><span data-stu-id="1a0b3-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
