---
title: Метод EmbedResource
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef7d6272c04c3edab8ef652bcb2759861ff2b982
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790056"
---
# <a name="embedresource-method"></a><span data-ttu-id="6caf2-102">Метод EmbedResource</span><span class="sxs-lookup"><span data-stu-id="6caf2-102">EmbedResource Method</span></span>
<span data-ttu-id="6caf2-103">Объявляет внедренного ресурса.</span><span class="sxs-lookup"><span data-stu-id="6caf2-103">Declares an embedded resource.</span></span> <span data-ttu-id="6caf2-104">Этот метод фактически не внедряет ресурс.</span><span class="sxs-lookup"><span data-stu-id="6caf2-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6caf2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6caf2-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6caf2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6caf2-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6caf2-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="6caf2-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6caf2-108">Файл токена или идентификатор сборки файла, содержащего ресурс.</span><span class="sxs-lookup"><span data-stu-id="6caf2-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="6caf2-109">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="6caf2-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="6caf2-110">Смещение ресурса от RVA.</span><span class="sxs-lookup"><span data-stu-id="6caf2-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6caf2-111">Специальные возможности, такие как флаги `mrPublic` и `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="6caf2-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="6caf2-112">Эти флаги может передаваться в [метод DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="6caf2-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6caf2-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6caf2-113">Return Value</span></span>  
 <span data-ttu-id="6caf2-114">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="6caf2-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6caf2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6caf2-115">Requirements</span></span>  
 <span data-ttu-id="6caf2-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="6caf2-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6caf2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6caf2-117">See also</span></span>

- [<span data-ttu-id="6caf2-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="6caf2-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6caf2-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="6caf2-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6caf2-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="6caf2-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
