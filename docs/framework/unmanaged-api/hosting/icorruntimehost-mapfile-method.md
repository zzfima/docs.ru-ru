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
ms.openlocfilehash: a8a979e86dbe52577d0b58089015338e4a87750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700180"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="76e7c-102">Метод ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="76e7c-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="76e7c-103">Сопоставляет указанный файл в память.</span><span class="sxs-lookup"><span data-stu-id="76e7c-103">Maps the specified file into memory.</span></span> <span data-ttu-id="76e7c-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="76e7c-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e7c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76e7c-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76e7c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="76e7c-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="76e7c-107">[in] Дескриптор файла для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="76e7c-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="76e7c-108">[out] Начальный адрес памяти, с которого начинается файла сопоставления.</span><span class="sxs-lookup"><span data-stu-id="76e7c-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e7c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="76e7c-109">Requirements</span></span>  
 <span data-ttu-id="76e7c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76e7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76e7c-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76e7c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76e7c-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76e7c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76e7c-113">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="76e7c-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e7c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="76e7c-114">See also</span></span>

- [<span data-ttu-id="76e7c-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="76e7c-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
