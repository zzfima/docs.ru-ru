---
title: Интерфейс IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4196ff2cb2d4ebc401076f603a8a7fdc9b9c76ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143797"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="28913-102">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="28913-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="28913-103">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="28913-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28913-104">Методы</span><span class="sxs-lookup"><span data-stu-id="28913-104">Methods</span></span>  
  
|<span data-ttu-id="28913-105">Метод</span><span class="sxs-lookup"><span data-stu-id="28913-105">Method</span></span>|<span data-ttu-id="28913-106">Описание</span><span class="sxs-lookup"><span data-stu-id="28913-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28913-107">Метод IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="28913-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="28913-108">Получает значение, указывающее, была ли обработана заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="28913-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="28913-109">Метод MarkToken</span><span class="sxs-lookup"><span data-stu-id="28913-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="28913-110">Задает значение, указывающее, что было обработано заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="28913-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="28913-111">Метод UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="28913-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="28913-112">Удаляет знаки обработки из всех маркеров в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="28913-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28913-113">Требования</span><span class="sxs-lookup"><span data-stu-id="28913-113">Requirements</span></span>  
 <span data-ttu-id="28913-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28913-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28913-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28913-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28913-116">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28913-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28913-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28913-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28913-118">См. также</span><span class="sxs-lookup"><span data-stu-id="28913-118">See also</span></span>

- [<span data-ttu-id="28913-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="28913-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
