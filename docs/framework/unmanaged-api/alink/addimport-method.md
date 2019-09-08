---
title: Метод AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787665"
---
# <a name="addimport-method"></a><span data-ttu-id="943d2-102">Метод AddImport</span><span class="sxs-lookup"><span data-stu-id="943d2-102">AddImport Method</span></span>
<span data-ttu-id="943d2-103">Добавляет в сборку импорты.</span><span class="sxs-lookup"><span data-stu-id="943d2-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="943d2-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="943d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="943d2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="943d2-106">Уникальный идентификатор сборки для дополнения.</span><span class="sxs-lookup"><span data-stu-id="943d2-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="943d2-107">Уникальный идентификатор, полученный из [метода ImportFile](importfile-method.md)импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="943d2-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="943d2-108">COM+ филедеф флаги, `ffContainsNoMetaData` такие `ffWriteable`как и.</span><span class="sxs-lookup"><span data-stu-id="943d2-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="943d2-109">`dwFlags`передается [методу дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="943d2-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="943d2-110">Указатель на токен, который получает идентификатор для результирующего файла.</span><span class="sxs-lookup"><span data-stu-id="943d2-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="943d2-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="943d2-111">Return Value</span></span>  
 <span data-ttu-id="943d2-112">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="943d2-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943d2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="943d2-113">Requirements</span></span>  
 <span data-ttu-id="943d2-114">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="943d2-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943d2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="943d2-115">See also</span></span>

- [<span data-ttu-id="943d2-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="943d2-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="943d2-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="943d2-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="943d2-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="943d2-118">ALink API</span></span>](index.md)
