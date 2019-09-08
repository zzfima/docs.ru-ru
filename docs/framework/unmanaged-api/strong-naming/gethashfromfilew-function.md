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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799195"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="e3650-102">Функция GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="e3650-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="e3650-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="e3650-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="e3650-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="e3650-104">This function has been deprecated.</span></span> <span data-ttu-id="e3650-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e3650-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3650-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3650-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="e3650-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3650-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e3650-108">окне Имя файла в Юникоде для хэширования.</span><span class="sxs-lookup"><span data-stu-id="e3650-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e3650-109">[вход, выход] Алгоритм, используемый при формировании хэша.</span><span class="sxs-lookup"><span data-stu-id="e3650-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="e3650-110">Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="e3650-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="e3650-111">Если `piHashAlg` параметр имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="e3650-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e3650-112">заполняет Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="e3650-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e3650-113">окне Максимальный размер буфера, `pbHash`на который указывает.</span><span class="sxs-lookup"><span data-stu-id="e3650-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e3650-114">заполняет Размер (в байтах `pbHash`).</span><span class="sxs-lookup"><span data-stu-id="e3650-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3650-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3650-115">Remarks</span></span>  
 <span data-ttu-id="e3650-116">Эта функция аналогична [GetHashFromFile](gethashfromfile-function.md), за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.</span><span class="sxs-lookup"><span data-stu-id="e3650-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3650-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e3650-117">Requirements</span></span>  
 <span data-ttu-id="e3650-118">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3650-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3650-119">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e3650-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e3650-120">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3650-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3650-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3650-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3650-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e3650-122">See also</span></span>

- [<span data-ttu-id="e3650-123">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="e3650-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="e3650-124">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="e3650-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="e3650-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e3650-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
