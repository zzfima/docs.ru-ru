---
title: Метод ICorRuntimeHost::MapFile
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 814073b766d5d562b414a566ae3f92abd664ce35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707847"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="dfb4a-102">Метод ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="dfb4a-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="dfb4a-103">Сопоставляет указанный файл в память.</span><span class="sxs-lookup"><span data-stu-id="dfb4a-103">Maps the specified file into memory.</span></span> <span data-ttu-id="dfb4a-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="dfb4a-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb4a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfb4a-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfb4a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfb4a-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="dfb4a-107">[in] Дескриптор файла для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dfb4a-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="dfb4a-108">[out] Начальный адрес памяти, с которого начинается файла сопоставления.</span><span class="sxs-lookup"><span data-stu-id="dfb4a-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb4a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dfb4a-109">Requirements</span></span>  
 <span data-ttu-id="dfb4a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb4a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb4a-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dfb4a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dfb4a-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dfb4a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dfb4a-113">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="dfb4a-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb4a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dfb4a-114">See also</span></span>
- [<span data-ttu-id="dfb4a-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="dfb4a-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
