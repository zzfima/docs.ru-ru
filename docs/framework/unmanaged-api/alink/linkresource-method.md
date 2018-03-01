---
title: "Метод LinkResource"
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
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1ff38bf0017cf400d8f35f0ddf265f8628c82d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="f0801-102">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="f0801-102">LinkResource Method</span></span>
<span data-ttu-id="f0801-103">Ссылки в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="f0801-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0801-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0801-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0801-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0801-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f0801-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="f0801-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="f0801-107">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="f0801-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="f0801-108">Необязательное имя нового файла.</span><span class="sxs-lookup"><span data-stu-id="f0801-108">Optional new file name.</span></span> <span data-ttu-id="f0801-109">Если значение не равно `pszFileName` pszNewLocation будут скопированы.</span><span class="sxs-lookup"><span data-stu-id="f0801-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="f0801-110">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="f0801-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f0801-111">Специальных возможностей, таких как флаги `mrPublic` и `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="f0801-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="f0801-112">Этот параметр может быть передан [метод DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="f0801-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0801-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f0801-113">Return Value</span></span>  
 <span data-ttu-id="f0801-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f0801-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0801-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f0801-115">Requirements</span></span>  
 <span data-ttu-id="f0801-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="f0801-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0801-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f0801-117">See Also</span></span>  
 [<span data-ttu-id="f0801-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f0801-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f0801-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f0801-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f0801-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="f0801-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
