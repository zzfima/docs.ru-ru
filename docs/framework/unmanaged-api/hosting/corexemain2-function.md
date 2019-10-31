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
ms.openlocfilehash: cc5324683daa9a02a6a89b2a3fb57ee9fd5dbe72
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136951"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="69fcc-102">Функция _CorExeMain2</span><span class="sxs-lookup"><span data-stu-id="69fcc-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="69fcc-103">Выполняет точку входа в указанном коде, сопоставленном с памятью.</span><span class="sxs-lookup"><span data-stu-id="69fcc-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="69fcc-104">Эта функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="69fcc-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69fcc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69fcc-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69fcc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="69fcc-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="69fcc-107">окне Указатель на код, сопоставленный с памятью.</span><span class="sxs-lookup"><span data-stu-id="69fcc-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="69fcc-108">окне Количество элементов, которые `pUnmappedPE` могут храниться.</span><span class="sxs-lookup"><span data-stu-id="69fcc-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="69fcc-109">окне Указатель на имя исполняемого образа.</span><span class="sxs-lookup"><span data-stu-id="69fcc-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="69fcc-110">окне Имя файла загрузчика.</span><span class="sxs-lookup"><span data-stu-id="69fcc-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="69fcc-111">окне Параметры командной строки, если они есть.</span><span class="sxs-lookup"><span data-stu-id="69fcc-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69fcc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="69fcc-112">Requirements</span></span>  
 <span data-ttu-id="69fcc-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69fcc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69fcc-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="69fcc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69fcc-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="69fcc-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69fcc-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69fcc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69fcc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="69fcc-117">See also</span></span>

- [<span data-ttu-id="69fcc-118">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="69fcc-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
