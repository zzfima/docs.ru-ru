---
title: "Метод GetAssemblyRefHash"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetAssemblyRefHash
api_location: alink.dll
api_type: COM
f1_keywords: GetAssemblyRefHash
helpviewer_keywords: GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99ae38025f223d669a428738783676ebc0687554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="13a40-102">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="13a40-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="13a40-103">Извлекает хэш-blob для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="13a40-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13a40-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13a40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13a40-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="13a40-106">Идентификатор сборки, на который будет ссылаться хэш.</span><span class="sxs-lookup"><span data-stu-id="13a40-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="13a40-107">Получает результирующее хэш-blob.</span><span class="sxs-lookup"><span data-stu-id="13a40-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="13a40-108">Получает размер в байтах хэш-blob.</span><span class="sxs-lookup"><span data-stu-id="13a40-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13a40-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13a40-109">Return Value</span></span>  
 <span data-ttu-id="13a40-110">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="13a40-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a40-111">Требования</span><span class="sxs-lookup"><span data-stu-id="13a40-111">Requirements</span></span>  
 <span data-ttu-id="13a40-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="13a40-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a40-113">См. также</span><span class="sxs-lookup"><span data-stu-id="13a40-113">See Also</span></span>  
 [<span data-ttu-id="13a40-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="13a40-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="13a40-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="13a40-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="13a40-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="13a40-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
