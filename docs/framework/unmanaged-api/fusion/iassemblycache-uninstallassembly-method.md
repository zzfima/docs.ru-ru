---
title: Метод IAssemblyCache::UninstallAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9991d1b6ffb1ab2c89acf54af3234d31c0e06907
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623745"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="a6f6f-102">Метод IAssemblyCache::UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="a6f6f-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="a6f6f-103">Удаляет указанную сборку из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="a6f6f-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f6f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6f6f-104">Syntax</span></span>  
  
```  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f6f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6f6f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="a6f6f-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="a6f6f-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="a6f6f-107">[in] Имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a6f6f-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="a6f6f-108">[in] Объект [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) структуру, содержащую данные для сборки.</span><span class="sxs-lookup"><span data-stu-id="a6f6f-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="a6f6f-109">[out, optional] Один из методов обработки значений, определенных в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="a6f6f-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="a6f6f-110">Ниже приведены возможные значения:</span><span class="sxs-lookup"><span data-stu-id="a6f6f-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="a6f6f-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="a6f6f-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="a6f6f-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="a6f6f-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="a6f6f-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="a6f6f-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="a6f6f-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="a6f6f-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="a6f6f-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="a6f6f-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="a6f6f-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="a6f6f-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f6f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a6f6f-117">Requirements</span></span>  
 <span data-ttu-id="a6f6f-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f6f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f6f-119">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a6f6f-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a6f6f-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f6f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f6f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a6f6f-121">See also</span></span>

- [<span data-ttu-id="a6f6f-122">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="a6f6f-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
