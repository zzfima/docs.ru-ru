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
ms.openlocfilehash: 48dd987896536006fe81bc01528cadb507123e27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049431"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="0aab0-102">Функция GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="0aab0-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="0aab0-103">Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="0aab0-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="0aab0-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="0aab0-104">This function has been deprecated.</span></span> <span data-ttu-id="0aab0-105">Используйте [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="0aab0-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aab0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0aab0-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0aab0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0aab0-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="0aab0-108">[in] Дескриптор файла, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="0aab0-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="0aab0-109">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="0aab0-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="0aab0-110">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0aab0-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="0aab0-111">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="0aab0-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="0aab0-112">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0aab0-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="0aab0-113">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0aab0-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aab0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0aab0-114">Requirements</span></span>  
 <span data-ttu-id="0aab0-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aab0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aab0-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0aab0-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0aab0-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0aab0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0aab0-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aab0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aab0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0aab0-119">See also</span></span>

- [<span data-ttu-id="0aab0-120">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="0aab0-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="0aab0-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0aab0-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
