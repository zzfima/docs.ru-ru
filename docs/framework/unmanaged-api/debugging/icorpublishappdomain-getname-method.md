---
title: Метод ICorPublishAppDomain::GetName
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b518a3be939c70b207a71d79a3d362dba26fd3d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774200"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="c510e-102">Метод ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="c510e-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="c510e-103">Возвращает имя домена приложения, представленного этим [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c510e-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c510e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c510e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c510e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c510e-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c510e-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="c510e-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c510e-107">[out] Указатель на число расширенных символов, включая символ null, возвращаются в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="c510e-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="c510e-108">[out] Массив, в котором для хранения имени.</span><span class="sxs-lookup"><span data-stu-id="c510e-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c510e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c510e-109">Remarks</span></span>  
 <span data-ttu-id="c510e-110">Если `szName` отлично от NULL, `GetName` метод копирует до `cchName` символов (включая завершающий символ null) в `szName`.</span><span class="sxs-lookup"><span data-stu-id="c510e-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="c510e-111">Если возвращается значение `pcchName`, фактическое число символов в имени (включая завершающий символ null) хранится в `szName` массива.</span><span class="sxs-lookup"><span data-stu-id="c510e-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="c510e-112">`GetName` Метод возвращает значение S_OK HRESULT, независимо от того, сколько символов были скопированы.</span><span class="sxs-lookup"><span data-stu-id="c510e-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c510e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c510e-113">Requirements</span></span>  
 <span data-ttu-id="c510e-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c510e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c510e-115">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c510e-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c510e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c510e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c510e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c510e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c510e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c510e-118">See also</span></span>

- [<span data-ttu-id="c510e-119">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="c510e-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
