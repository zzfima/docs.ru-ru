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
ms.openlocfilehash: 0e1975a5063217299ddbcdce6f625d5a1285d5b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642559"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="31ba4-102">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="31ba4-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="31ba4-103">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="31ba4-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31ba4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="31ba4-104">Methods</span></span>  
  
|<span data-ttu-id="31ba4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="31ba4-105">Method</span></span>|<span data-ttu-id="31ba4-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="31ba4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31ba4-107">Метод IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="31ba4-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="31ba4-108">Получает значение, указывающее, была ли обработана заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="31ba4-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="31ba4-109">Метод MarkToken</span><span class="sxs-lookup"><span data-stu-id="31ba4-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="31ba4-110">Задает значение, указывающее, что было обработано заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="31ba4-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="31ba4-111">Метод UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="31ba4-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="31ba4-112">Удаляет знаки обработки из всех маркеров в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="31ba4-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31ba4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="31ba4-113">Requirements</span></span>  
 <span data-ttu-id="31ba4-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31ba4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ba4-115">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="31ba4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31ba4-116">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31ba4-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31ba4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ba4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ba4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="31ba4-118">See also</span></span>
- [<span data-ttu-id="31ba4-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="31ba4-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
