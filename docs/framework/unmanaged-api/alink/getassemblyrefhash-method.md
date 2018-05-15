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
ms.openlocfilehash: ccf60d067af356dda1870a2fb1dcca21966f16a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="1a70f-102">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="1a70f-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="1a70f-103">Извлекает хэш-blob для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="1a70f-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a70f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a70f-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a70f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a70f-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="1a70f-106">Идентификатор сборки, на который будет ссылаться хэш.</span><span class="sxs-lookup"><span data-stu-id="1a70f-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="1a70f-107">Получает результирующее хэш-blob.</span><span class="sxs-lookup"><span data-stu-id="1a70f-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="1a70f-108">Получает размер в байтах хэш-blob.</span><span class="sxs-lookup"><span data-stu-id="1a70f-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a70f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a70f-109">Return Value</span></span>  
 <span data-ttu-id="1a70f-110">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="1a70f-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a70f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1a70f-111">Requirements</span></span>  
 <span data-ttu-id="1a70f-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="1a70f-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a70f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1a70f-113">See Also</span></span>  
 [<span data-ttu-id="1a70f-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="1a70f-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1a70f-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="1a70f-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1a70f-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="1a70f-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
