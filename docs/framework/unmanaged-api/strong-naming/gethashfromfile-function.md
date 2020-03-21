---
title: Функция GetHashFromFile
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176985"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="18114-102">Функция GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="18114-102">GetHashFromFile Function</span></span>
<span data-ttu-id="18114-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="18114-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="18114-104">Эта функция была амортизирована.</span><span class="sxs-lookup"><span data-stu-id="18114-104">This function has been deprecated.</span></span> <span data-ttu-id="18114-105">Вместо этого используйте метод [ICLRStrongName::GetHashFromFile.](../hosting/iclrstrongname-gethashfromfile-method.md)</span><span class="sxs-lookup"><span data-stu-id="18114-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18114-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18114-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18114-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="18114-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="18114-108">(в) Название файла хэшу.</span><span class="sxs-lookup"><span data-stu-id="18114-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="18114-109">(в, вне) Алгоритм для использования при генерации хэша.</span><span class="sxs-lookup"><span data-stu-id="18114-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="18114-110">Действительные алгоритмы определяются Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="18114-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="18114-111">Если `piHashAlg` установлен до 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="18114-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="18114-112">(ваут) Массив байта, содержащий генерируемый хэш.</span><span class="sxs-lookup"><span data-stu-id="18114-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="18114-113">(в) Максимальный размер буфера, на который `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="18114-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="18114-114">(ваут) Размер, в байтах, `pbHash`возвращенного .</span><span class="sxs-lookup"><span data-stu-id="18114-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18114-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="18114-115">Remarks</span></span>  
 <span data-ttu-id="18114-116">Эта функция такая же, как [GetHashFromFileW](gethashfromfilew-function.md), за исключением того, что спецификация имени файла ANSI вместо Unicode.</span><span class="sxs-lookup"><span data-stu-id="18114-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18114-117">Требования</span><span class="sxs-lookup"><span data-stu-id="18114-117">Requirements</span></span>  
 <span data-ttu-id="18114-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18114-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18114-119">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="18114-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="18114-120">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18114-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18114-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18114-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18114-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18114-122">See also</span></span>

- [<span data-ttu-id="18114-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="18114-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="18114-124">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="18114-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="18114-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="18114-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
