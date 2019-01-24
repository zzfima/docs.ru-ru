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
ms.openlocfilehash: fe2f683ae46d1ee6205f97536976a358e86fc53d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720383"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="b85ba-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="b85ba-102">IMetaDataError Interface</span></span>
<span data-ttu-id="b85ba-103">Предоставляет механизм обратного вызова для сообщений об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="b85ba-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b85ba-104">`IMetaDataError` Интерфейс должен быть реализован с помощью клиента.</span><span class="sxs-lookup"><span data-stu-id="b85ba-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b85ba-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b85ba-105">Methods</span></span>  
  
|<span data-ttu-id="b85ba-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b85ba-106">Method</span></span>|<span data-ttu-id="b85ba-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b85ba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b85ba-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="b85ba-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="b85ba-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="b85ba-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b85ba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b85ba-110">Requirements</span></span>  
 <span data-ttu-id="b85ba-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b85ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b85ba-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b85ba-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b85ba-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b85ba-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b85ba-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b85ba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85ba-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b85ba-115">See also</span></span>
- [<span data-ttu-id="b85ba-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="b85ba-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
