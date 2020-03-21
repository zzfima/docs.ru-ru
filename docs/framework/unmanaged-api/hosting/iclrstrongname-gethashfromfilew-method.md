---
title: Метод ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176374"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="84fbf-102">Метод ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="84fbf-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="84fbf-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="84fbf-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84fbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84fbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="84fbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84fbf-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="84fbf-106">(в) Имя файла Unicode хэша.</span><span class="sxs-lookup"><span data-stu-id="84fbf-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="84fbf-107">(в, вне) Алгоритм для использования при генерации хэша.</span><span class="sxs-lookup"><span data-stu-id="84fbf-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="84fbf-108">Действительные алгоритмы определяются Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="84fbf-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="84fbf-109">Если `piHashAlg` установлен до 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="84fbf-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="84fbf-110">(ваут) Массив байта, содержащий генерируемый хэш.</span><span class="sxs-lookup"><span data-stu-id="84fbf-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="84fbf-111">(в) Максимальный размер буфера, `pbHash`на который указывает .</span><span class="sxs-lookup"><span data-stu-id="84fbf-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="84fbf-112">(ваут) Размер, в байтах, из `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="84fbf-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84fbf-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84fbf-113">Return Value</span></span>  
 <span data-ttu-id="84fbf-114">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="84fbf-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84fbf-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="84fbf-115">Remarks</span></span>  
 <span data-ttu-id="84fbf-116">Этот метод такой же, как [метод ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) метод, за исключением того, что спецификация имени файла Unicode вместо ANSI.</span><span class="sxs-lookup"><span data-stu-id="84fbf-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84fbf-117">Требования</span><span class="sxs-lookup"><span data-stu-id="84fbf-117">Requirements</span></span>  
 <span data-ttu-id="84fbf-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84fbf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84fbf-119">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="84fbf-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="84fbf-120">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84fbf-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84fbf-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84fbf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84fbf-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84fbf-122">See also</span></span>

- [<span data-ttu-id="84fbf-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="84fbf-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="84fbf-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="84fbf-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
