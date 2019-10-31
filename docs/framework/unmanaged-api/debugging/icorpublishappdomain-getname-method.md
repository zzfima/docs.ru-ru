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
ms.openlocfilehash: 2f91891164f1f80617cab10347eb4a7a08762c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140354"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="2f73d-102">Метод ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="2f73d-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="2f73d-103">Возвращает имя домена приложения, представленного этим [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f73d-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f73d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f73d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f73d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f73d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2f73d-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="2f73d-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2f73d-107">заполняет Указатель на число расширенных символов, включая символ null, возвращенный в массиве `szName`.</span><span class="sxs-lookup"><span data-stu-id="2f73d-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="2f73d-108">заполняет Массив, в котором сохраняется имя.</span><span class="sxs-lookup"><span data-stu-id="2f73d-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f73d-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="2f73d-109">Remarks</span></span>  
 <span data-ttu-id="2f73d-110">Если `szName` не равно null, метод `GetName` копирует в `szName``cchName` символы (включая знак завершения null).</span><span class="sxs-lookup"><span data-stu-id="2f73d-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="2f73d-111">Если в `pcchName`возвращается значение, отличное от NULL, фактическое число символов в имени (включая знак завершения null) сохраняется в массиве `szName`.</span><span class="sxs-lookup"><span data-stu-id="2f73d-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="2f73d-112">Метод `GetName` возвращает значение S_OK HRESULT независимо от того, сколько символов было скопировано.</span><span class="sxs-lookup"><span data-stu-id="2f73d-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f73d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2f73d-113">Requirements</span></span>  
 <span data-ttu-id="2f73d-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f73d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f73d-115">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="2f73d-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2f73d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f73d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f73d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f73d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f73d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2f73d-118">See also</span></span>

- [<span data-ttu-id="2f73d-119">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="2f73d-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
