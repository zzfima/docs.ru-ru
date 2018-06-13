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
ms.openlocfilehash: ad77aba02c819749794534ca2ecd478661bc363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444985"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="c30ee-102">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="c30ee-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="c30ee-103">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="c30ee-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c30ee-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c30ee-104">Methods</span></span>  
  
|<span data-ttu-id="c30ee-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c30ee-105">Method</span></span>|<span data-ttu-id="c30ee-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c30ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c30ee-107">Метод IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="c30ee-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="c30ee-108">Возвращает значение, указывающее, была ли обработана указанным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="c30ee-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="c30ee-109">Метод MarkToken</span><span class="sxs-lookup"><span data-stu-id="c30ee-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="c30ee-110">Задает значение, указывающее, что указанный токен метаданных был обработан.</span><span class="sxs-lookup"><span data-stu-id="c30ee-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="c30ee-111">Метод UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="c30ee-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="c30ee-112">Удаляет знаки обработки изо всех маркеров в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c30ee-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c30ee-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c30ee-113">Requirements</span></span>  
 <span data-ttu-id="c30ee-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c30ee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c30ee-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c30ee-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c30ee-116">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c30ee-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c30ee-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c30ee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30ee-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c30ee-118">See Also</span></span>  
 [<span data-ttu-id="c30ee-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="c30ee-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
