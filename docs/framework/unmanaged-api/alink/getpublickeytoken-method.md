---
title: Метод GetPublicKeyToken
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0481cfc3fa88aeb6fd7cd6ba93554d426f8eb2e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492053"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="edc64-102">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="edc64-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="edc64-103">Извлекает токен открытого ключа для заданного файла или контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="edc64-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edc64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edc64-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="edc64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="edc64-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="edc64-106">Имя файла ключа.</span><span class="sxs-lookup"><span data-stu-id="edc64-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="edc64-107">Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="edc64-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="edc64-108">Адрес, где будет храниться ключ.</span><span class="sxs-lookup"><span data-stu-id="edc64-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="edc64-109">Указывает размер в байтах буфера, обозначается `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="edc64-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="edc64-110">По возвращении содержит фактическое число байтов, используемых.</span><span class="sxs-lookup"><span data-stu-id="edc64-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edc64-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="edc64-111">Return Value</span></span>  
 <span data-ttu-id="edc64-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="edc64-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edc64-113">Требования</span><span class="sxs-lookup"><span data-stu-id="edc64-113">Requirements</span></span>  
 <span data-ttu-id="edc64-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="edc64-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc64-115">См. также</span><span class="sxs-lookup"><span data-stu-id="edc64-115">See also</span></span>
- [<span data-ttu-id="edc64-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="edc64-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="edc64-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="edc64-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="edc64-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="edc64-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
