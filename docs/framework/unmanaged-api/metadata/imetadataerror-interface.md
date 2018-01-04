---
title: "Интерфейс IMetaDataError"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError
helpviewer_keywords: IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4df7aa7400a180151de5420effc8738955d51c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="822d7-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="822d7-102">IMetaDataError Interface</span></span>
<span data-ttu-id="822d7-103">Предоставляет механизм обратного вызова для сообщения об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="822d7-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="822d7-104">`IMetaDataError` Интерфейс должен быть реализован клиентом.</span><span class="sxs-lookup"><span data-stu-id="822d7-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="822d7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="822d7-105">Methods</span></span>  
  
|<span data-ttu-id="822d7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="822d7-106">Method</span></span>|<span data-ttu-id="822d7-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="822d7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="822d7-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="822d7-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="822d7-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="822d7-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="822d7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="822d7-110">Requirements</span></span>  
 <span data-ttu-id="822d7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="822d7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="822d7-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="822d7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="822d7-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="822d7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="822d7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="822d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="822d7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="822d7-115">See Also</span></span>  
 [<span data-ttu-id="822d7-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="822d7-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
