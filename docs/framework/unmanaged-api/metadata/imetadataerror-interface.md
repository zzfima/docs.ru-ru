---
title: Интерфейс IMetaDataError
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277b93267f0537c8e499a8d8f3b456c4396a975c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966344"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="8c72a-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="8c72a-102">IMetaDataError Interface</span></span>
<span data-ttu-id="8c72a-103">Предоставляет механизм обратного вызова для сообщения об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="8c72a-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c72a-104">`IMetaDataError` Интерфейс должен быть реализован клиентом.</span><span class="sxs-lookup"><span data-stu-id="8c72a-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c72a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8c72a-105">Methods</span></span>  
  
|<span data-ttu-id="8c72a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8c72a-106">Method</span></span>|<span data-ttu-id="8c72a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8c72a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c72a-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="8c72a-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="8c72a-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="8c72a-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c72a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8c72a-110">Requirements</span></span>  
 <span data-ttu-id="8c72a-111">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c72a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c72a-112">**Заголовок.** COR. h</span><span class="sxs-lookup"><span data-stu-id="8c72a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c72a-113">**Библиотечная** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8c72a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c72a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c72a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c72a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8c72a-115">See also</span></span>

- [<span data-ttu-id="8c72a-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="8c72a-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
