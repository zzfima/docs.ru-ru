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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188634"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="cec43-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="cec43-102">IMetaDataError Interface</span></span>
<span data-ttu-id="cec43-103">Предоставляет механизм обратного вызова для сообщений об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="cec43-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cec43-104">`IMetaDataError` Интерфейс должен быть реализован с помощью клиента.</span><span class="sxs-lookup"><span data-stu-id="cec43-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cec43-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cec43-105">Methods</span></span>  
  
|<span data-ttu-id="cec43-106">Метод</span><span class="sxs-lookup"><span data-stu-id="cec43-106">Method</span></span>|<span data-ttu-id="cec43-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cec43-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cec43-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="cec43-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="cec43-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="cec43-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cec43-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cec43-110">Requirements</span></span>  
 <span data-ttu-id="cec43-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cec43-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cec43-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cec43-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cec43-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cec43-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cec43-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cec43-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec43-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cec43-115">See also</span></span>

- [<span data-ttu-id="cec43-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="cec43-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
