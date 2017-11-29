---
title: "Метод ICorRuntimeHost::MapFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd156aac23cdca446bcf2666ce36e91fef6d5392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="f2bf5-102">Метод ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="f2bf5-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="f2bf5-103">Сопоставляет указанный файл в память.</span><span class="sxs-lookup"><span data-stu-id="f2bf5-103">Maps the specified file into memory.</span></span> <span data-ttu-id="f2bf5-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="f2bf5-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2bf5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2bf5-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2bf5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2bf5-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f2bf5-107">[in] Дескриптор файла для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="f2bf5-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="f2bf5-108">[out] Начальный адрес памяти, с которого начинается файл сопоставления.</span><span class="sxs-lookup"><span data-stu-id="f2bf5-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2bf5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f2bf5-109">Requirements</span></span>  
 <span data-ttu-id="f2bf5-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2bf5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2bf5-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2bf5-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2bf5-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2bf5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2bf5-113">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="f2bf5-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bf5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f2bf5-114">See Also</span></span>  
 [<span data-ttu-id="f2bf5-115">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f2bf5-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
