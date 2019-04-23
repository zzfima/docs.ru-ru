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
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215772"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="e4f63-102">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="e4f63-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="e4f63-103">Извлекает токен открытого ключа для заданного файла или контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="e4f63-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4f63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4f63-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4f63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4f63-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="e4f63-106">Имя файла ключа.</span><span class="sxs-lookup"><span data-stu-id="e4f63-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="e4f63-107">Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="e4f63-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="e4f63-108">Адрес, где будет храниться ключ.</span><span class="sxs-lookup"><span data-stu-id="e4f63-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="e4f63-109">Указывает размер в байтах буфера, обозначается `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="e4f63-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="e4f63-110">По возвращении содержит фактическое число байтов, используемых.</span><span class="sxs-lookup"><span data-stu-id="e4f63-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4f63-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e4f63-111">Return Value</span></span>  
 <span data-ttu-id="e4f63-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e4f63-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4f63-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e4f63-113">Requirements</span></span>  
 <span data-ttu-id="e4f63-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="e4f63-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f63-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e4f63-115">See also</span></span>

- [<span data-ttu-id="e4f63-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e4f63-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e4f63-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e4f63-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e4f63-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="e4f63-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
