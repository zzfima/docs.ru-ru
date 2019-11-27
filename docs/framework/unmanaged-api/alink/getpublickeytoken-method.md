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
ms.openlocfilehash: 2e7ed4e1529104db30b0b06665f74342d9ca9a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447240"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="a1c53-102">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="a1c53-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="a1c53-103">Извлекает токен открытого ключа для данного ключа или контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="a1c53-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1c53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1c53-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1c53-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="a1c53-106">Имя файла ключа.</span><span class="sxs-lookup"><span data-stu-id="a1c53-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="a1c53-107">Имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="a1c53-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="a1c53-108">Адрес, по которому должен храниться токен ключа.</span><span class="sxs-lookup"><span data-stu-id="a1c53-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="a1c53-109">Задает размер (в байтах) буфера, указанного `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="a1c53-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="a1c53-110">После возврата содержит фактическое число используемых байтов.</span><span class="sxs-lookup"><span data-stu-id="a1c53-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1c53-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a1c53-111">Return Value</span></span>  
 <span data-ttu-id="a1c53-112">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a1c53-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c53-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a1c53-113">Requirements</span></span>  
 <span data-ttu-id="a1c53-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="a1c53-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c53-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1c53-115">See also</span></span>

- [<span data-ttu-id="a1c53-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a1c53-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a1c53-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a1c53-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a1c53-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="a1c53-118">ALink API</span></span>](index.md)
