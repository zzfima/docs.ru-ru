---
title: Функция GetHashFromHandle
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: dc241324f5844610d7b86b7cb9668f84d4525395
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140661"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="9b0cc-102">Функция GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="9b0cc-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="9b0cc-103">Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="9b0cc-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-104">This function has been deprecated.</span></span> <span data-ttu-id="9b0cc-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9b0cc-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b0cc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b0cc-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b0cc-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b0cc-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="9b0cc-108">окне Описатель файла для хэширования.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9b0cc-109">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="9b0cc-110">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9b0cc-111">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9b0cc-112">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9b0cc-113">заполняет Размер возвращаемого `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="9b0cc-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b0cc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9b0cc-114">Requirements</span></span>  
 <span data-ttu-id="9b0cc-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b0cc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b0cc-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="9b0cc-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9b0cc-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9b0cc-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b0cc-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b0cc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0cc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9b0cc-119">See also</span></span>

- [<span data-ttu-id="9b0cc-120">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="9b0cc-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="9b0cc-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9b0cc-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
