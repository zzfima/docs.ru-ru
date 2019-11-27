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
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440163"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="6d2e4-102">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="6d2e4-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="6d2e4-103">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="6d2e4-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d2e4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6d2e4-104">Methods</span></span>  
  
|<span data-ttu-id="6d2e4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6d2e4-105">Method</span></span>|<span data-ttu-id="6d2e4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6d2e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d2e4-107">Метод IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="6d2e4-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="6d2e4-108">Возвращает значение, указывающее, был ли обработан заданный маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="6d2e4-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="6d2e4-109">Метод MarkToken</span><span class="sxs-lookup"><span data-stu-id="6d2e4-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="6d2e4-110">Задает значение, указывающее, что указанный токен метаданных был обработан.</span><span class="sxs-lookup"><span data-stu-id="6d2e4-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="6d2e4-111">Метод UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="6d2e4-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="6d2e4-112">Удаляет метки обработки из всех токенов в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="6d2e4-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d2e4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6d2e4-113">Requirements</span></span>  
 <span data-ttu-id="6d2e4-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d2e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d2e4-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6d2e4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d2e4-116">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6d2e4-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d2e4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d2e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2e4-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d2e4-118">See also</span></span>

- [<span data-ttu-id="6d2e4-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="6d2e4-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
