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
ms.openlocfilehash: 5f6140e5f85a7ee21773c96a5abdccadaddab92e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777457"
---
# <a name="embedresource-method"></a><span data-ttu-id="9fcde-102">Метод EmbedResource</span><span class="sxs-lookup"><span data-stu-id="9fcde-102">EmbedResource Method</span></span>
<span data-ttu-id="9fcde-103">Объявляет внедренный ресурс.</span><span class="sxs-lookup"><span data-stu-id="9fcde-103">Declares an embedded resource.</span></span> <span data-ttu-id="9fcde-104">Этот метод фактически не внедряет ресурс.</span><span class="sxs-lookup"><span data-stu-id="9fcde-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcde-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fcde-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fcde-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fcde-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9fcde-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="9fcde-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9fcde-108">Маркер файла или идентификатор сборки файла, содержащего ресурс.</span><span class="sxs-lookup"><span data-stu-id="9fcde-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="9fcde-109">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="9fcde-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="9fcde-110">Смещение ресурса от RVA.</span><span class="sxs-lookup"><span data-stu-id="9fcde-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9fcde-111">Флаги специальных возможностей `mrPublic` , `mrPrivate`такие как и.</span><span class="sxs-lookup"><span data-stu-id="9fcde-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="9fcde-112">Эти флаги можно передать в [метод дефиникспортедтипе](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="9fcde-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fcde-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9fcde-113">Return Value</span></span>  
 <span data-ttu-id="9fcde-114">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="9fcde-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fcde-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9fcde-115">Requirements</span></span>  
 <span data-ttu-id="9fcde-116">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="9fcde-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcde-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9fcde-117">See also</span></span>

- [<span data-ttu-id="9fcde-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="9fcde-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9fcde-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="9fcde-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9fcde-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="9fcde-120">ALink API</span></span>](index.md)
