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
ms.openlocfilehash: d924dbf21a0f0b046c8d8f8f294e91bc5ff6c015
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869415"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="91c5d-102">Метод ICorProfilerInfo::GetTokenAndMetadataFromFunction</span><span class="sxs-lookup"><span data-stu-id="91c5d-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="91c5d-103">Возвращает маркер метаданных и экземпляр интерфейса метаданных, который может использоваться для токена указанной функции.</span><span class="sxs-lookup"><span data-stu-id="91c5d-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c5d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91c5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91c5d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="91c5d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="91c5d-106">окне Идентификатор функции, для которой необходимо получить токен метаданных и интерфейс метаданных.</span><span class="sxs-lookup"><span data-stu-id="91c5d-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="91c5d-107">окне Идентификатор ссылки интерфейса метаданных для получения экземпляра.</span><span class="sxs-lookup"><span data-stu-id="91c5d-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="91c5d-108">заполняет Указатель на адрес экземпляра интерфейса метаданных, который может использоваться с токеном для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="91c5d-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="91c5d-109">заполняет Указатель на маркер метаданных для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="91c5d-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91c5d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="91c5d-110">Requirements</span></span>  
 <span data-ttu-id="91c5d-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91c5d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91c5d-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="91c5d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="91c5d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91c5d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91c5d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91c5d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c5d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="91c5d-115">See also</span></span>

- [<span data-ttu-id="91c5d-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="91c5d-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
