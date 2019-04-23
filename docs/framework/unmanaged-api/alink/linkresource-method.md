---
title: Метод LinkResource
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079440"
---
# <a name="linkresource-method"></a><span data-ttu-id="e5195-102">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="e5195-102">LinkResource Method</span></span>
<span data-ttu-id="e5195-103">Ссылки в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="e5195-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5195-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5195-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5195-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5195-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e5195-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="e5195-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="e5195-107">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="e5195-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="e5195-108">Необязательное имя нового файла.</span><span class="sxs-lookup"><span data-stu-id="e5195-108">Optional new file name.</span></span> <span data-ttu-id="e5195-109">Если не NULL, `pszFileName` pszNewLocation будут скопированы.</span><span class="sxs-lookup"><span data-stu-id="e5195-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="e5195-110">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="e5195-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e5195-111">Специальные возможности, такие как флаги `mrPublic` и `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="e5195-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="e5195-112">Этот параметр может передаваться в [метод DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="e5195-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5195-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5195-113">Return Value</span></span>  
 <span data-ttu-id="e5195-114">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e5195-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5195-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e5195-115">Requirements</span></span>  
 <span data-ttu-id="e5195-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="e5195-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5195-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e5195-117">See also</span></span>

- [<span data-ttu-id="e5195-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e5195-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e5195-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e5195-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e5195-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="e5195-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
