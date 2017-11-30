---
title: "Метод EmbedResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location: alink.dll
api_type: COM
f1_keywords: EmbedResource
helpviewer_keywords: EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 98dbd32452184bf4f832bd66ffebb0fcf3d5bb0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="9570c-102">Метод EmbedResource</span><span class="sxs-lookup"><span data-stu-id="9570c-102">EmbedResource Method</span></span>
<span data-ttu-id="9570c-103">Объявляет внедренный ресурс.</span><span class="sxs-lookup"><span data-stu-id="9570c-103">Declares an embedded resource.</span></span> <span data-ttu-id="9570c-104">Этот метод фактически не внедрять ресурса.</span><span class="sxs-lookup"><span data-stu-id="9570c-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9570c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9570c-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9570c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9570c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9570c-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="9570c-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9570c-108">Маркер файла или сборки идентификатор файла, содержащего ресурс.</span><span class="sxs-lookup"><span data-stu-id="9570c-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="9570c-109">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="9570c-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="9570c-110">Смещение ресурса от RVA.</span><span class="sxs-lookup"><span data-stu-id="9570c-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9570c-111">Специальных возможностей, таких как флаги `mrPublic` и `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="9570c-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="9570c-112">Эти флаги могут быть переданы [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="9570c-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9570c-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9570c-113">Return Value</span></span>  
 <span data-ttu-id="9570c-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="9570c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9570c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9570c-115">Requirements</span></span>  
 <span data-ttu-id="9570c-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="9570c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9570c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9570c-117">See Also</span></span>  
 [<span data-ttu-id="9570c-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="9570c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9570c-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="9570c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9570c-120">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="9570c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
