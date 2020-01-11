---
title: Метод ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: d98181e0d43206bfbf96182d7e4acf33da486348
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901179"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="cf9e9-102">Метод ICLRStrongName::GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="cf9e9-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="cf9e9-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf9e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf9e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf9e9-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cf9e9-106">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="cf9e9-107">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cf9e9-108">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cf9e9-109">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cf9e9-110">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cf9e9-111">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cf9e9-112">заполняет Возвращаемый размер `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="cf9e9-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf9e9-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cf9e9-113">Return Value</span></span>  
 <span data-ttu-id="cf9e9-114">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="cf9e9-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9e9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="cf9e9-115">Requirements</span></span>  
 <span data-ttu-id="cf9e9-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf9e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9e9-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="cf9e9-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cf9e9-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf9e9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf9e9-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf9e9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9e9-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf9e9-120">See also</span></span>

- [<span data-ttu-id="cf9e9-121">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="cf9e9-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="cf9e9-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cf9e9-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
