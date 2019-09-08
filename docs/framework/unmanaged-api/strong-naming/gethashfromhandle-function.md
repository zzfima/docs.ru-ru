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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eac353252f5a97402cbd883895b3e397c39edd6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799180"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="11786-102">Функция GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="11786-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="11786-103">Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="11786-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="11786-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="11786-104">This function has been deprecated.</span></span> <span data-ttu-id="11786-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11786-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11786-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11786-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11786-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="11786-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="11786-108">окне Описатель файла для хэширования.</span><span class="sxs-lookup"><span data-stu-id="11786-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="11786-109">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="11786-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="11786-110">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11786-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="11786-111">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="11786-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="11786-112">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="11786-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="11786-113">заполняет Размер возвращаемого `pbHash`объекта (в байтах).</span><span class="sxs-lookup"><span data-stu-id="11786-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11786-114">Требования</span><span class="sxs-lookup"><span data-stu-id="11786-114">Requirements</span></span>  
 <span data-ttu-id="11786-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11786-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11786-116">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="11786-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="11786-117">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="11786-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11786-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11786-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11786-119">См. также</span><span class="sxs-lookup"><span data-stu-id="11786-119">See also</span></span>

- [<span data-ttu-id="11786-120">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="11786-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="11786-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="11786-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
