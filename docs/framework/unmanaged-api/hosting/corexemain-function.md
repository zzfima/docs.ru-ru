---
title: Функция _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63af5979b113f81c01c9c68d6cccdfa10811265a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corexemain-function"></a><span data-ttu-id="bd7b6-102">Функция _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="bd7b6-102">_CorExeMain Function</span></span>
<span data-ttu-id="bd7b6-103">Инициализирует общеязыковой среды выполнения (CLR), находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd7b6-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bd7b6-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd7b6-105">Remarks</span></span>  
 <span data-ttu-id="bd7b6-106">Эта функция вызывается загрузчиком в процессах, созданных из управляемых сборок исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="bd7b6-107">DLL-сборки, загрузчик вызывает [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="bd7b6-108">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле образа.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="bd7b6-109">В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorExeMain` функция косвенно через адресную привязку в загрузчик операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="bd7b6-110">Во всех других версиях Windows он вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="bd7b6-111">Дополнительные сведения см. в разделе «Примечания» в [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="bd7b6-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd7b6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bd7b6-112">Requirements</span></span>  
 <span data-ttu-id="bd7b6-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd7b6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd7b6-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd7b6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd7b6-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd7b6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd7b6-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd7b6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7b6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bd7b6-117">See Also</span></span>  
 [<span data-ttu-id="bd7b6-118">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="bd7b6-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
