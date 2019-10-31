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
ms.openlocfilehash: bcf1b49f0576f5dbd73c001f8edff7a9ab29af22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139524"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="1dec1-102">Метод ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="1dec1-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="1dec1-103">Сопоставляет указанный файл с памятью.</span><span class="sxs-lookup"><span data-stu-id="1dec1-103">Maps the specified file into memory.</span></span> <span data-ttu-id="1dec1-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="1dec1-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dec1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1dec1-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dec1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1dec1-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="1dec1-107">окне Описатель файла для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="1dec1-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="1dec1-108">заполняет Начальный адрес памяти, с которого начинается сопоставление файла.</span><span class="sxs-lookup"><span data-stu-id="1dec1-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dec1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1dec1-109">Requirements</span></span>  
 <span data-ttu-id="1dec1-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dec1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dec1-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1dec1-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1dec1-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1dec1-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dec1-113">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="1dec1-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dec1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1dec1-114">See also</span></span>

- [<span data-ttu-id="1dec1-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="1dec1-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
