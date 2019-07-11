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
ms.openlocfilehash: ec2c357cd56670f4f2deed8023bed7842a7f4ed7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741881"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="890af-102">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="890af-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="890af-103">Извлекает токен открытого ключа для заданного файла или контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="890af-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="890af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="890af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="890af-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="890af-106">Имя файла ключа.</span><span class="sxs-lookup"><span data-stu-id="890af-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="890af-107">Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="890af-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="890af-108">Адрес, где будет храниться ключ.</span><span class="sxs-lookup"><span data-stu-id="890af-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="890af-109">Указывает размер в байтах буфера, обозначается `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="890af-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="890af-110">По возвращении содержит фактическое число байтов, используемых.</span><span class="sxs-lookup"><span data-stu-id="890af-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="890af-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="890af-111">Return Value</span></span>  
 <span data-ttu-id="890af-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="890af-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="890af-113">Требования</span><span class="sxs-lookup"><span data-stu-id="890af-113">Requirements</span></span>  
 <span data-ttu-id="890af-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="890af-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890af-115">См. также</span><span class="sxs-lookup"><span data-stu-id="890af-115">See also</span></span>

- [<span data-ttu-id="890af-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="890af-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="890af-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="890af-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="890af-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="890af-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
