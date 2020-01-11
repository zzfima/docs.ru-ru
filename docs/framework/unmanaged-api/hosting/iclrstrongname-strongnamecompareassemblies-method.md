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
ms.openlocfilehash: 16b51393c945061efb0e94e48e5388c60472ee11
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899745"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="eba4d-102">Метод ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="eba4d-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="eba4d-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="eba4d-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eba4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eba4d-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eba4d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eba4d-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="eba4d-106">окне Путь к первой сборке.</span><span class="sxs-lookup"><span data-stu-id="eba4d-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="eba4d-107">окне Путь к второй сборке.</span><span class="sxs-lookup"><span data-stu-id="eba4d-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="eba4d-108">заполняет Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="eba4d-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="eba4d-109">`SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="eba4d-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="eba4d-110">`SN_CMP_IDENTICAL` (1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="eba4d-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="eba4d-111">`SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.</span><span class="sxs-lookup"><span data-stu-id="eba4d-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eba4d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eba4d-112">Return Value</span></span>  
 <span data-ttu-id="eba4d-113">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="eba4d-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eba4d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="eba4d-114">Requirements</span></span>  
 <span data-ttu-id="eba4d-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eba4d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eba4d-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="eba4d-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="eba4d-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eba4d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eba4d-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eba4d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eba4d-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="eba4d-119">Remarks</span></span>  
 <span data-ttu-id="eba4d-120">Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="eba4d-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba4d-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="eba4d-121">See also</span></span>

- [<span data-ttu-id="eba4d-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="eba4d-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
