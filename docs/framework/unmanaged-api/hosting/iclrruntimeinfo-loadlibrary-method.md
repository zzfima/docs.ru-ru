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
ms.openlocfilehash: 8c72f58bb65bd862b0625bfa0398b26bad0197e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192087"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="1af9a-102">Метод ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="1af9a-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="1af9a-103">Загружает библиотеку .NET Framework из среды CLR, представленной интерфейсом [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1af9a-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="1af9a-104">Этот метод заменяет функцию [лоадлибраришим](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1af9a-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af9a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1af9a-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1af9a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1af9a-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="1af9a-107">окне Имя загружаемой сборки.</span><span class="sxs-lookup"><span data-stu-id="1af9a-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="1af9a-108">заполняет Маркер загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="1af9a-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1af9a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1af9a-109">Return Value</span></span>  
 <span data-ttu-id="1af9a-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="1af9a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1af9a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1af9a-111">HRESULT</span></span>|<span data-ttu-id="1af9a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1af9a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1af9a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1af9a-113">S_OK</span></span>|<span data-ttu-id="1af9a-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="1af9a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1af9a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1af9a-115">E_POINTER</span></span>|<span data-ttu-id="1af9a-116">`pwzDllName` или `phndModule` равно null.</span><span class="sxs-lookup"><span data-stu-id="1af9a-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="1af9a-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1af9a-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1af9a-118">Недостаточно памяти для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="1af9a-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1af9a-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="1af9a-119">Remarks</span></span>  
 <span data-ttu-id="1af9a-120">Этот метод загружает только библиотеки DLL, входящие в распространяемый пакет .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1af9a-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="1af9a-121">Он не может загружать сборки, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="1af9a-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af9a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1af9a-122">Requirements</span></span>  
 <span data-ttu-id="1af9a-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1af9a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af9a-124">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="1af9a-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1af9a-125">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1af9a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1af9a-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af9a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af9a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1af9a-127">See also</span></span>

- [<span data-ttu-id="1af9a-128">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="1af9a-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1af9a-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1af9a-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1af9a-130">Размещение</span><span class="sxs-lookup"><span data-stu-id="1af9a-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
