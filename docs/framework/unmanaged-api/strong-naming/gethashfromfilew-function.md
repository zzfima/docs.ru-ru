---
title: Функция GetHashFromFileW
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175087"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="8513c-102">Функция GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="8513c-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="8513c-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="8513c-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="8513c-104">Эта функция была амортизирована.</span><span class="sxs-lookup"><span data-stu-id="8513c-104">This function has been deprecated.</span></span> <span data-ttu-id="8513c-105">Вместо этого используйте метод [ICLRStrongName::GetHashFromFileW.](../hosting/iclrstrongname-gethashfromfilew-method.md)</span><span class="sxs-lookup"><span data-stu-id="8513c-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8513c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8513c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="8513c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8513c-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8513c-108">(в) Имя файла Unicode хэша.</span><span class="sxs-lookup"><span data-stu-id="8513c-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8513c-109">(в, вне) Алгоритм для использования при генерации хэша.</span><span class="sxs-lookup"><span data-stu-id="8513c-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="8513c-110">Действительные алгоритмы определяются Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="8513c-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="8513c-111">Если `piHashAlg` установлен до 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="8513c-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8513c-112">(ваут) Массив байта, содержащий генерируемый хэш.</span><span class="sxs-lookup"><span data-stu-id="8513c-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8513c-113">(в) Максимальный размер буфера, `pbHash`на который указывает .</span><span class="sxs-lookup"><span data-stu-id="8513c-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8513c-114">(ваут) Размер, в байтах, из `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="8513c-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8513c-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="8513c-115">Remarks</span></span>  
 <span data-ttu-id="8513c-116">Эта функция такая же, как [GetHashFromFile](gethashfromfile-function.md), за исключением того, что спецификация имени файла Unicode вместо ANSI.</span><span class="sxs-lookup"><span data-stu-id="8513c-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8513c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8513c-117">Requirements</span></span>  
 <span data-ttu-id="8513c-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8513c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8513c-119">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8513c-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8513c-120">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8513c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8513c-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8513c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8513c-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8513c-122">See also</span></span>

- [<span data-ttu-id="8513c-123">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="8513c-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="8513c-124">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="8513c-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="8513c-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8513c-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
