---
title: Метод ICLRStrongName::StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eb23da5accd89931ee4b883bfa162035ec26ddd
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861040"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="84a73-102">Метод ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="84a73-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="84a73-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="84a73-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a73-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84a73-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84a73-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84a73-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="84a73-106">[in] Путь к первой сборки.</span><span class="sxs-lookup"><span data-stu-id="84a73-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="84a73-107">[in] Путь к вторую сборку.</span><span class="sxs-lookup"><span data-stu-id="84a73-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="84a73-108">[out] Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="84a73-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="84a73-109">`SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат разные данные.</span><span class="sxs-lookup"><span data-stu-id="84a73-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="84a73-110">`SN_CMP_IDENTICAL` (1) — указывает, что сборки идентичны, включая их подписи и контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="84a73-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="84a73-111">`SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только подпись и контрольная сумма.</span><span class="sxs-lookup"><span data-stu-id="84a73-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84a73-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84a73-112">Return Value</span></span>  
 <span data-ttu-id="84a73-113">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="84a73-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a73-114">Требования</span><span class="sxs-lookup"><span data-stu-id="84a73-114">Requirements</span></span>  
 <span data-ttu-id="84a73-115">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a73-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a73-116">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="84a73-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="84a73-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84a73-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84a73-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a73-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84a73-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="84a73-119">Remarks</span></span>  
 <span data-ttu-id="84a73-120">Подпись строгого имени сборки состоит из текстовое имя сборки, версию, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="84a73-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a73-121">См. также</span><span class="sxs-lookup"><span data-stu-id="84a73-121">See Also</span></span>  
 [<span data-ttu-id="84a73-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="84a73-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
