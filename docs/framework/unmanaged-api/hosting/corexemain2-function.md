---
title: Функция _CorExeMain2
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef51ad511d1b7d8064d4bd141e2952bf723afff7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501686"
---
# <a name="corexemain2-function"></a><span data-ttu-id="82e0c-102">Функция _CorExeMain2</span><span class="sxs-lookup"><span data-stu-id="82e0c-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="82e0c-103">Выполняет точку входа в указанном коде отображения памяти.</span><span class="sxs-lookup"><span data-stu-id="82e0c-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="82e0c-104">Эта функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="82e0c-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e0c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82e0c-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82e0c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="82e0c-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="82e0c-107">[in] Указатель на код, размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="82e0c-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="82e0c-108">[in] Число элементов `pUnmappedPE` может содержать.</span><span class="sxs-lookup"><span data-stu-id="82e0c-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="82e0c-109">[in] Указатель на имя исполняемого образа.</span><span class="sxs-lookup"><span data-stu-id="82e0c-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="82e0c-110">[in] Имя файла загрузчика.</span><span class="sxs-lookup"><span data-stu-id="82e0c-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="82e0c-111">[in] Параметры командной строки, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="82e0c-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82e0c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="82e0c-112">Requirements</span></span>  
 <span data-ttu-id="82e0c-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82e0c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e0c-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82e0c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82e0c-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82e0c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82e0c-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e0c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="82e0c-117">See also</span></span>
- [<span data-ttu-id="82e0c-118">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="82e0c-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
