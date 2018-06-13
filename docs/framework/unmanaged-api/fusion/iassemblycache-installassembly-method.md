---
title: Метод IAssemblyCache::InstallAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 726a4ed8ee3d451687e0af671d948eb7648f7f58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430028"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="009ad-102">Метод IAssemblyCache::InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="009ad-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="009ad-103">Устанавливает указанную сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="009ad-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="009ad-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="009ad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="009ad-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="009ad-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="009ad-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="009ad-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="009ad-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="009ad-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="009ad-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="009ad-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="009ad-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="009ad-110">[in] Путь к манифест сборки для установки.</span><span class="sxs-lookup"><span data-stu-id="009ad-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="009ad-111">[in] Объект [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) структура, содержащая данные для установки.</span><span class="sxs-lookup"><span data-stu-id="009ad-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009ad-112">Требования</span><span class="sxs-lookup"><span data-stu-id="009ad-112">Requirements</span></span>  
 <span data-ttu-id="009ad-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009ad-114">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="009ad-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="009ad-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009ad-116">См. также</span><span class="sxs-lookup"><span data-stu-id="009ad-116">See Also</span></span>  
 [<span data-ttu-id="009ad-117">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="009ad-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
