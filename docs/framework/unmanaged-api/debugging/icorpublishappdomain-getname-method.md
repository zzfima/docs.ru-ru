---
title: "Метод ICorPublishAppDomain::GetName"
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
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9808d99406f2b83a6ee4e4a634210bf9c894bfd7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="ae589-102">Метод ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="ae589-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="ae589-103">Возвращает имя домена приложения, представленный этим [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ae589-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae589-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae589-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae589-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae589-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ae589-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="ae589-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ae589-107">[out] Указатель на число расширенных символов, включая символ null, возвращаются в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="ae589-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="ae589-108">[out] Массив для хранения имени.</span><span class="sxs-lookup"><span data-stu-id="ae589-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae589-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae589-109">Remarks</span></span>  
 <span data-ttu-id="ae589-110">Если `szName` отлично от null, `GetName` метод копирует до `cchName` символов (включая завершающий символ null) в `szName`.</span><span class="sxs-lookup"><span data-stu-id="ae589-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="ae589-111">Если ненулевое значение возвращается в `pcchName`, фактическое число символов в имени (включая завершающий символ null) хранится в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="ae589-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="ae589-112">`GetName` Метод возвращает значение S_OK HRESULT независимо от того, сколько символов были скопированы.</span><span class="sxs-lookup"><span data-stu-id="ae589-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae589-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ae589-113">Requirements</span></span>  
 <span data-ttu-id="ae589-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae589-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae589-115">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ae589-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ae589-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae589-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae589-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae589-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae589-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ae589-118">See Also</span></span>  
 [<span data-ttu-id="ae589-119">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="ae589-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
