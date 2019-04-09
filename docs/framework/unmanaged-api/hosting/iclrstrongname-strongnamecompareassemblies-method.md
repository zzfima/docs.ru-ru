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
ms.openlocfilehash: 63d4b885b6968b800bc965a9be1ec6b795a42220
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140664"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="47ffb-102">Метод ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="47ffb-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="47ffb-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="47ffb-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ffb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47ffb-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47ffb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47ffb-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="47ffb-106">[in] Путь к первой сборки.</span><span class="sxs-lookup"><span data-stu-id="47ffb-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="47ffb-107">[in] Путь к вторую сборку.</span><span class="sxs-lookup"><span data-stu-id="47ffb-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="47ffb-108">[out] Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="47ffb-108">[out] One of the following values:</span></span>  
  
-   `SN_CMP_DIFFERENT` <span data-ttu-id="47ffb-109">(0) — указывает, что сборки содержат разные данные.</span><span class="sxs-lookup"><span data-stu-id="47ffb-109">(0) - Specifies that the assemblies contain different data.</span></span>  
  
-   `SN_CMP_IDENTICAL` <span data-ttu-id="47ffb-110">(1) — указывает, что сборки идентичны, включая их подписи и контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="47ffb-110">(1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   `SN_CMP_SIGONLY` <span data-ttu-id="47ffb-111">(2) — указывает, что сборки отличаются только подпись и контрольная сумма.</span><span class="sxs-lookup"><span data-stu-id="47ffb-111">(2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47ffb-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47ffb-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="47ffb-113">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="47ffb-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47ffb-114">Требования</span><span class="sxs-lookup"><span data-stu-id="47ffb-114">Requirements</span></span>  
 <span data-ttu-id="47ffb-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47ffb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47ffb-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="47ffb-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="47ffb-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47ffb-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="47ffb-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="47ffb-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="47ffb-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="47ffb-119">Remarks</span></span>  
 <span data-ttu-id="47ffb-120">Подпись строгого имени сборки состоит из текстовое имя сборки, версию, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="47ffb-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ffb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="47ffb-121">See also</span></span>

- [<span data-ttu-id="47ffb-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="47ffb-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
