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
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445631"
---
# <a name="linkresource-method"></a><span data-ttu-id="8de46-102">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="8de46-102">LinkResource Method</span></span>
<span data-ttu-id="8de46-103">Links in a resource.</span><span class="sxs-lookup"><span data-stu-id="8de46-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8de46-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8de46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8de46-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8de46-106">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="8de46-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="8de46-107">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="8de46-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="8de46-108">Optional new file name.</span><span class="sxs-lookup"><span data-stu-id="8de46-108">Optional new file name.</span></span> <span data-ttu-id="8de46-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="8de46-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="8de46-110">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="8de46-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8de46-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="8de46-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="8de46-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="8de46-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8de46-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8de46-113">Return Value</span></span>  
 <span data-ttu-id="8de46-114">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="8de46-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de46-115">Требования</span><span class="sxs-lookup"><span data-stu-id="8de46-115">Requirements</span></span>  
 <span data-ttu-id="8de46-116">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="8de46-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de46-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8de46-117">See also</span></span>

- [<span data-ttu-id="8de46-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="8de46-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8de46-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="8de46-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8de46-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="8de46-120">ALink API</span></span>](index.md)
