---
title: "Метод EmbedResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 815e4b6abbb56b0998a12c096f0ba7cb678778ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="a0ba6-102">Метод EmbedResource</span><span class="sxs-lookup"><span data-stu-id="a0ba6-102">EmbedResource Method</span></span>
<span data-ttu-id="a0ba6-103">Объявляет внедренный ресурс.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-103">Declares an embedded resource.</span></span> <span data-ttu-id="a0ba6-104">Этот метод фактически не внедрять ресурса.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ba6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0ba6-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0ba6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0ba6-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a0ba6-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a0ba6-108">Маркер файла или сборки идентификатор файла, содержащего ресурс.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="a0ba6-109">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="a0ba6-110">Смещение ресурса от RVA.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a0ba6-111">Специальных возможностей, таких как флаги `mrPublic` и `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="a0ba6-112">Эти флаги могут быть переданы [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a0ba6-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0ba6-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0ba6-113">Return Value</span></span>  
 <span data-ttu-id="a0ba6-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ba6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a0ba6-115">Requirements</span></span>  
 <span data-ttu-id="a0ba6-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="a0ba6-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ba6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a0ba6-117">See Also</span></span>  
 [<span data-ttu-id="a0ba6-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a0ba6-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a0ba6-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a0ba6-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a0ba6-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="a0ba6-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
