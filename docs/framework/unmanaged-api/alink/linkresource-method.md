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
ms.openlocfilehash: 4f75ebc3a40bddbaf2347b9ef559139888f83900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401112"
---
# <a name="linkresource-method"></a><span data-ttu-id="cd47a-102">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="cd47a-102">LinkResource Method</span></span>
<span data-ttu-id="cd47a-103">Ссылки в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="cd47a-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd47a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd47a-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd47a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd47a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cd47a-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="cd47a-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="cd47a-107">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="cd47a-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="cd47a-108">Необязательное имя нового файла.</span><span class="sxs-lookup"><span data-stu-id="cd47a-108">Optional new file name.</span></span> <span data-ttu-id="cd47a-109">Если значение не равно `pszFileName` pszNewLocation будут скопированы.</span><span class="sxs-lookup"><span data-stu-id="cd47a-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="cd47a-110">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="cd47a-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cd47a-111">Специальных возможностей, таких как флаги `mrPublic` и `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="cd47a-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="cd47a-112">Этот параметр может быть передан [метод DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="cd47a-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd47a-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cd47a-113">Return Value</span></span>  
 <span data-ttu-id="cd47a-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="cd47a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd47a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="cd47a-115">Requirements</span></span>  
 <span data-ttu-id="cd47a-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="cd47a-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd47a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cd47a-117">See Also</span></span>  
 [<span data-ttu-id="cd47a-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="cd47a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="cd47a-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="cd47a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="cd47a-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="cd47a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
