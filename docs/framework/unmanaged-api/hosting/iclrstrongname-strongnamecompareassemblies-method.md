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
ms.openlocfilehash: fdca03b781e07b709cbc54e673dbaa2a1130fbe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135149"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="9dda2-102">Метод ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="9dda2-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="9dda2-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="9dda2-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dda2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dda2-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dda2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dda2-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="9dda2-106">окне Путь к первой сборке.</span><span class="sxs-lookup"><span data-stu-id="9dda2-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="9dda2-107">окне Путь к второй сборке.</span><span class="sxs-lookup"><span data-stu-id="9dda2-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="9dda2-108">заполняет Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9dda2-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="9dda2-109">`SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="9dda2-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="9dda2-110">`SN_CMP_IDENTICAL` (1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="9dda2-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="9dda2-111">`SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.</span><span class="sxs-lookup"><span data-stu-id="9dda2-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dda2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9dda2-112">Return Value</span></span>  
 <span data-ttu-id="9dda2-113">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="9dda2-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dda2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9dda2-114">Requirements</span></span>  
 <span data-ttu-id="9dda2-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dda2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dda2-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="9dda2-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9dda2-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9dda2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dda2-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dda2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dda2-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="9dda2-119">Remarks</span></span>  
 <span data-ttu-id="9dda2-120">Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9dda2-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dda2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9dda2-121">See also</span></span>

- [<span data-ttu-id="9dda2-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9dda2-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
