---
title: Метод ICLRStrongName::GetHashFromBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 0c9adcc252fe16c95da8b2afca45bb2ee5dc545a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135207"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="d50af-102">Метод ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d50af-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="d50af-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="d50af-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d50af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d50af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d50af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d50af-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="d50af-106">окне Указатель на адрес блока памяти, который необходимо хэшировать.</span><span class="sxs-lookup"><span data-stu-id="d50af-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="d50af-107">окне Длина блока памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="d50af-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d50af-108">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="d50af-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d50af-109">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d50af-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d50af-110">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="d50af-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d50af-111">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d50af-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d50af-112">заполняет Размер возвращаемого `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="d50af-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d50af-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d50af-113">Return Value</span></span>  
 <span data-ttu-id="d50af-114">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="d50af-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d50af-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d50af-115">Requirements</span></span>  
 <span data-ttu-id="d50af-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d50af-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d50af-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="d50af-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d50af-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d50af-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d50af-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d50af-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50af-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d50af-120">See also</span></span>

- [<span data-ttu-id="d50af-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d50af-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
