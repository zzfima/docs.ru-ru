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
ms.openlocfilehash: 8541e7761e2f8e1839d028fdaea3eb71307ba615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131204"
---
# <a name="_corexemain-function"></a><span data-ttu-id="1fb15-102">Функция _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="1fb15-102">_CorExeMain Function</span></span>
<span data-ttu-id="1fb15-103">Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="1fb15-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fb15-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1fb15-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="1fb15-105">Remarks</span></span>  
 <span data-ttu-id="1fb15-106">Эта функция вызывается загрузчиком в процессах, созданных из управляемых исполняемых сборок.</span><span class="sxs-lookup"><span data-stu-id="1fb15-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="1fb15-107">Для сборок DLL загрузчик вызывает функцию [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1fb15-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="1fb15-108">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле изображения.</span><span class="sxs-lookup"><span data-stu-id="1fb15-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="1fb15-109">В Windows 98, Windows ME, Windows NT и Windows 2000 функция `_CorExeMain` вызывается непрямо через исправление в загрузчике операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1fb15-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="1fb15-110">Во всех остальных версиях Windows он вызывается непосредственно загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1fb15-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="1fb15-111">Дополнительные сведения см. в подразделе "Примечания" раздела [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1fb15-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb15-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1fb15-112">Requirements</span></span>  
 <span data-ttu-id="1fb15-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fb15-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb15-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1fb15-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1fb15-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1fb15-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1fb15-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb15-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb15-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1fb15-117">See also</span></span>

- [<span data-ttu-id="1fb15-118">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="1fb15-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
