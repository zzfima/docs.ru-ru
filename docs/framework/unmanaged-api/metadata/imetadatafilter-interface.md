---
title: "Интерфейс IMetaDataFilter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7c0afbb9be9af3ffe69ddfcac85b70de53a391ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="403ce-102">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="403ce-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="403ce-103">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="403ce-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="403ce-104">Методы</span><span class="sxs-lookup"><span data-stu-id="403ce-104">Methods</span></span>  
  
|<span data-ttu-id="403ce-105">Метод</span><span class="sxs-lookup"><span data-stu-id="403ce-105">Method</span></span>|<span data-ttu-id="403ce-106">Описание</span><span class="sxs-lookup"><span data-stu-id="403ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="403ce-107">Метод IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="403ce-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="403ce-108">Возвращает значение, указывающее, была ли обработана указанным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="403ce-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="403ce-109">Метод MarkToken</span><span class="sxs-lookup"><span data-stu-id="403ce-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="403ce-110">Задает значение, указывающее, что указанный токен метаданных был обработан.</span><span class="sxs-lookup"><span data-stu-id="403ce-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="403ce-111">Метод UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="403ce-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="403ce-112">Удаляет знаки обработки изо всех маркеров в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="403ce-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="403ce-113">Требования</span><span class="sxs-lookup"><span data-stu-id="403ce-113">Requirements</span></span>  
 <span data-ttu-id="403ce-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="403ce-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="403ce-115">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="403ce-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="403ce-116">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="403ce-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="403ce-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="403ce-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="403ce-118">См. также</span><span class="sxs-lookup"><span data-stu-id="403ce-118">See Also</span></span>  
 [<span data-ttu-id="403ce-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="403ce-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
