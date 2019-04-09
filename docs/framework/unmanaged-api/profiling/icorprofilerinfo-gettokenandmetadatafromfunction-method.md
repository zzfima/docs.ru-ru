---
title: Метод ICorProfilerInfo::GetTokenAndMetadataFromFunction
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e7f2e8247d3ba822cc09a98f985926e6b5400c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206893"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="ff433-102">Метод ICorProfilerInfo::GetTokenAndMetadataFromFunction</span><span class="sxs-lookup"><span data-stu-id="ff433-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="ff433-103">Получает маркер метаданных и экземпляр интерфейса метаданных, который может использоваться в отношении маркера для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="ff433-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff433-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff433-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff433-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff433-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ff433-106">[in] Идентификатор функции, для которого необходимо получить токен метаданных и интерфейс метаданных.</span><span class="sxs-lookup"><span data-stu-id="ff433-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="ff433-107">[in] Идентификатор ссылки на интерфейс метаданных для получения экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ff433-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="ff433-108">[out] Указатель на адрес экземпляр интерфейса метаданных, который может использоваться в отношении маркера для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="ff433-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="ff433-109">[out] Указатель на токен метаданных для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="ff433-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff433-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ff433-110">Requirements</span></span>  
 <span data-ttu-id="ff433-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff433-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff433-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff433-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff433-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff433-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ff433-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ff433-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff433-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ff433-115">See also</span></span>

- [<span data-ttu-id="ff433-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ff433-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
