---
title: Метод ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 8131a9838cc958405ca23c75c702db5ec65a41c8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901191"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="26e33-102">Метод ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="26e33-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="26e33-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="26e33-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26e33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26e33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26e33-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="26e33-106">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="26e33-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="26e33-107">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="26e33-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="26e33-108">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="26e33-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="26e33-109">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="26e33-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="26e33-110">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="26e33-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="26e33-111">заполняет Возвращаемый размер `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="26e33-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26e33-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="26e33-112">Return Value</span></span>  
 <span data-ttu-id="26e33-113">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="26e33-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e33-114">Требования</span><span class="sxs-lookup"><span data-stu-id="26e33-114">Requirements</span></span>  
 <span data-ttu-id="26e33-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e33-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e33-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="26e33-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="26e33-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="26e33-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26e33-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e33-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e33-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="26e33-119">See also</span></span>

- [<span data-ttu-id="26e33-120">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="26e33-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="26e33-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="26e33-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
