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
ms.openlocfilehash: 37f1f6055ec8fa68fe804780d2893d20c978e6bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188634"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="d2851-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="d2851-102">IMetaDataError Interface</span></span>
<span data-ttu-id="d2851-103">Предоставляет механизм обратного вызова для сообщений об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="d2851-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2851-104">`IMetaDataError` Интерфейс должен быть реализован с помощью клиента.</span><span class="sxs-lookup"><span data-stu-id="d2851-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2851-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d2851-105">Methods</span></span>  
  
|<span data-ttu-id="d2851-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d2851-106">Method</span></span>|<span data-ttu-id="d2851-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d2851-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2851-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="d2851-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="d2851-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="d2851-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2851-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d2851-110">Requirements</span></span>  
 <span data-ttu-id="d2851-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2851-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2851-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2851-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2851-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2851-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d2851-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d2851-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2851-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d2851-115">See also</span></span>

- [<span data-ttu-id="d2851-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="d2851-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
