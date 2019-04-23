---
title: Метод IAssemblyCache::QueryAssemblyInfo
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81b647032b2e9474e3b4472552ed884cec92ffc3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216433"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="83b00-102">Метод IAssemblyCache::QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="83b00-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="83b00-103">Получает запрашиваемые данные об указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="83b00-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83b00-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83b00-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83b00-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="83b00-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="83b00-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="83b00-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="83b00-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="83b00-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="83b00-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="83b00-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="83b00-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="83b00-110">[in] Имя сборки, для которого будут извлечены данные.</span><span class="sxs-lookup"><span data-stu-id="83b00-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="83b00-111">[in, out] [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) структура, содержащая данные о сборке.</span><span class="sxs-lookup"><span data-stu-id="83b00-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b00-112">Требования</span><span class="sxs-lookup"><span data-stu-id="83b00-112">Requirements</span></span>  
 <span data-ttu-id="83b00-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83b00-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b00-114">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="83b00-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="83b00-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b00-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b00-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83b00-116">See also</span></span>

- [<span data-ttu-id="83b00-117">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="83b00-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
