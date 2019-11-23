---
title: Метод AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446681"
---
# <a name="addfile-method"></a><span data-ttu-id="74510-102">Метод AddFile</span><span class="sxs-lookup"><span data-stu-id="74510-102">AddFile Method</span></span>
<span data-ttu-id="74510-103">Adds files to the assembly.</span><span class="sxs-lookup"><span data-stu-id="74510-103">Adds files to the assembly.</span></span> <span data-ttu-id="74510-104">Can also be used to create unbound modules.</span><span class="sxs-lookup"><span data-stu-id="74510-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74510-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74510-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="74510-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="74510-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="74510-107">Unique ID of the assembly to be augmented.</span><span class="sxs-lookup"><span data-stu-id="74510-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="74510-108">Fully qualified name of file to be added.</span><span class="sxs-lookup"><span data-stu-id="74510-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="74510-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="74510-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="74510-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="74510-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="74510-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span><span class="sxs-lookup"><span data-stu-id="74510-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="74510-112">Pointer to where the unique ID of the added file will be stored.</span><span class="sxs-lookup"><span data-stu-id="74510-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74510-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="74510-113">Return Value</span></span>  
 <span data-ttu-id="74510-114">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="74510-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74510-115">Требования</span><span class="sxs-lookup"><span data-stu-id="74510-115">Requirements</span></span>  
 <span data-ttu-id="74510-116">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="74510-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74510-117">См. также</span><span class="sxs-lookup"><span data-stu-id="74510-117">See also</span></span>

- [<span data-ttu-id="74510-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="74510-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="74510-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="74510-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="74510-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="74510-120">ALink API</span></span>](index.md)
