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
ms.openlocfilehash: d19eebaa3aa0ebb6f9807f0cf277b7ed6183c148
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777196"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="5cfc1-102">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="5cfc1-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="5cfc1-103">Извлекает хэш-объект хэша для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="5cfc1-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cfc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cfc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cfc1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cfc1-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="5cfc1-106">Идентификатор сборки, на которую будет ссылаться хэш.</span><span class="sxs-lookup"><span data-stu-id="5cfc1-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="5cfc1-107">Получает результирующий большой двоичный объект хэша.</span><span class="sxs-lookup"><span data-stu-id="5cfc1-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="5cfc1-108">Получает размер хэш-объекта хэша (в байтах).</span><span class="sxs-lookup"><span data-stu-id="5cfc1-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cfc1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5cfc1-109">Return Value</span></span>  
 <span data-ttu-id="5cfc1-110">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="5cfc1-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cfc1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5cfc1-111">Requirements</span></span>  
 <span data-ttu-id="5cfc1-112">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="5cfc1-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cfc1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5cfc1-113">See also</span></span>

- [<span data-ttu-id="5cfc1-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="5cfc1-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5cfc1-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="5cfc1-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5cfc1-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="5cfc1-116">ALink API</span></span>](index.md)
