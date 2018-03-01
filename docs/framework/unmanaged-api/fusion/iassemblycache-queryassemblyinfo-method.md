---
title: "Метод IAssemblyCache::QueryAssemblyInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66e09f805b120239eef764b8cd61835e713e236c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="38c12-102">Метод IAssemblyCache::QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="38c12-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="38c12-103">Возвращает запрашиваемые данные об указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="38c12-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38c12-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38c12-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38c12-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="38c12-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="38c12-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="38c12-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="38c12-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="38c12-108">QUERYASMINFO_FLAG_VALIDATE (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="38c12-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="38c12-109">QUERYASMINFO_FLAG_GETSIZE (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="38c12-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="38c12-110">[in] Имя сборки, для которого будут извлекаться данные.</span><span class="sxs-lookup"><span data-stu-id="38c12-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="38c12-111">[in, out] [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) структура, содержащая данные о сборке.</span><span class="sxs-lookup"><span data-stu-id="38c12-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38c12-112">Требования</span><span class="sxs-lookup"><span data-stu-id="38c12-112">Requirements</span></span>  
 <span data-ttu-id="38c12-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38c12-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c12-114">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="38c12-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="38c12-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c12-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c12-116">См. также</span><span class="sxs-lookup"><span data-stu-id="38c12-116">See Also</span></span>  
 [<span data-ttu-id="38c12-117">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="38c12-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
