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
ms.openlocfilehash: 95c65e73c118b5358ac0a92dd0a1ca5545558e73
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796804"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="8bf6b-102">Метод IAssemblyCache::InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="8bf6b-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="8bf6b-103">Устанавливает указанную сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8bf6b-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bf6b-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bf6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bf6b-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="8bf6b-106">окне Флаги, определенные в Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="8bf6b-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="8bf6b-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8bf6b-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="8bf6b-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="8bf6b-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="8bf6b-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="8bf6b-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="8bf6b-110">окне Путь к манифесту для устанавливаемой сборки.</span><span class="sxs-lookup"><span data-stu-id="8bf6b-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="8bf6b-111">окне Структура [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) , содержащая данные для установки.</span><span class="sxs-lookup"><span data-stu-id="8bf6b-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf6b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8bf6b-112">Requirements</span></span>  
 <span data-ttu-id="8bf6b-113">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bf6b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf6b-114">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8bf6b-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8bf6b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf6b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8bf6b-116">See also</span></span>

- [<span data-ttu-id="8bf6b-117">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="8bf6b-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
