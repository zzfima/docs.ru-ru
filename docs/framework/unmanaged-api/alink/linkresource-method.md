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
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776954"
---
# <a name="linkresource-method"></a><span data-ttu-id="a19c4-102">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="a19c4-102">LinkResource Method</span></span>
<span data-ttu-id="a19c4-103">Ссылки в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="a19c4-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a19c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a19c4-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a19c4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a19c4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a19c4-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="a19c4-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="a19c4-107">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="a19c4-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="a19c4-108">Необязательное новое имя файла.</span><span class="sxs-lookup"><span data-stu-id="a19c4-108">Optional new file name.</span></span> <span data-ttu-id="a19c4-109">Если значение не равно NULL `pszFileName` , будет скопировано в псзневлокатион.</span><span class="sxs-lookup"><span data-stu-id="a19c4-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="a19c4-110">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="a19c4-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a19c4-111">Флаги специальных возможностей `mrPublic` , `mrPrivate`такие как и.</span><span class="sxs-lookup"><span data-stu-id="a19c4-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="a19c4-112">Этот параметр может быть передан [методу DefineManifestResource](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="a19c4-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a19c4-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a19c4-113">Return Value</span></span>  
 <span data-ttu-id="a19c4-114">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="a19c4-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a19c4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a19c4-115">Requirements</span></span>  
 <span data-ttu-id="a19c4-116">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="a19c4-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19c4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a19c4-117">See also</span></span>

- [<span data-ttu-id="a19c4-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a19c4-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a19c4-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a19c4-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a19c4-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="a19c4-120">ALink API</span></span>](index.md)
