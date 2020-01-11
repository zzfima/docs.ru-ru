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
ms.openlocfilehash: e5821abed4d6c7f7595bad3240ab86d5a128d794
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901148"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="988ed-102">Метод ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="988ed-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="988ed-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="988ed-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="988ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="988ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="988ed-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="988ed-106">окне Имя файла в Юникоде для хэширования.</span><span class="sxs-lookup"><span data-stu-id="988ed-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="988ed-107">[вход, выход] Алгоритм, используемый при формировании хэша.</span><span class="sxs-lookup"><span data-stu-id="988ed-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="988ed-108">Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="988ed-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="988ed-109">Если `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="988ed-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="988ed-110">заполняет Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="988ed-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="988ed-111">окне Максимальный размер буфера, на который указывает `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="988ed-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="988ed-112">заполняет Размер `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="988ed-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="988ed-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="988ed-113">Return Value</span></span>  
 <span data-ttu-id="988ed-114">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="988ed-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="988ed-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="988ed-115">Remarks</span></span>  
 <span data-ttu-id="988ed-116">Этот метод аналогичен методу [метод iclrstrongname:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) , за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.</span><span class="sxs-lookup"><span data-stu-id="988ed-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988ed-117">Требования</span><span class="sxs-lookup"><span data-stu-id="988ed-117">Requirements</span></span>  
 <span data-ttu-id="988ed-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988ed-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988ed-119">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="988ed-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="988ed-120">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="988ed-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="988ed-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988ed-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988ed-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="988ed-122">See also</span></span>

- [<span data-ttu-id="988ed-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="988ed-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="988ed-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="988ed-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
