---
title: Метод GetAssemblyRefHash
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fa8d42f9e849db6a02f6c62b37e04cf5dee016e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119656"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="16c24-102">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="16c24-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="16c24-103">Извлекает большой двоичный объект хэша для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="16c24-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16c24-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="16c24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16c24-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="16c24-106">Идентификатор сборки, в которую будет ссылаться хэш.</span><span class="sxs-lookup"><span data-stu-id="16c24-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="16c24-107">Получает результирующее большого двоичного объекта хэша.</span><span class="sxs-lookup"><span data-stu-id="16c24-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="16c24-108">Получает размер в байтах, большого двоичного объекта хэша.</span><span class="sxs-lookup"><span data-stu-id="16c24-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16c24-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16c24-109">Return Value</span></span>  
 <span data-ttu-id="16c24-110">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="16c24-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c24-111">Требования</span><span class="sxs-lookup"><span data-stu-id="16c24-111">Requirements</span></span>  
 <span data-ttu-id="16c24-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="16c24-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c24-113">См. также</span><span class="sxs-lookup"><span data-stu-id="16c24-113">See also</span></span>

- [<span data-ttu-id="16c24-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="16c24-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="16c24-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="16c24-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="16c24-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="16c24-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
