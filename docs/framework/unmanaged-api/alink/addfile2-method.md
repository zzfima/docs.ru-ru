---
title: Метод AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de85d264d709da747fab636f40c99bc0d0752251
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742355"
---
# <a name="addfile2-method"></a><span data-ttu-id="56f56-102">Метод AddFile2</span><span class="sxs-lookup"><span data-stu-id="56f56-102">AddFile2 Method</span></span>
<span data-ttu-id="56f56-103">Добавляет файлы в сборку.</span><span class="sxs-lookup"><span data-stu-id="56f56-103">Adds files to the assembly.</span></span> <span data-ttu-id="56f56-104">Может также использоваться для создания несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="56f56-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f56-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56f56-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="56f56-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="56f56-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="56f56-107">Идентификатор сборки, к которому добавляется файл.</span><span class="sxs-lookup"><span data-stu-id="56f56-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="56f56-108">Имя файла для добавления.</span><span class="sxs-lookup"><span data-stu-id="56f56-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="56f56-109">COM + `FileDef` флаги, такие как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="56f56-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="56f56-110">`dwFlags` передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="56f56-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="56f56-111">Интерфейс для [интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="56f56-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="56f56-112">Получает идентификатор для добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="56f56-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56f56-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56f56-113">Return Value</span></span>  
 <span data-ttu-id="56f56-114">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="56f56-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f56-115">Требования</span><span class="sxs-lookup"><span data-stu-id="56f56-115">Requirements</span></span>  
 <span data-ttu-id="56f56-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="56f56-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f56-117">См. также</span><span class="sxs-lookup"><span data-stu-id="56f56-117">See also</span></span>

- [<span data-ttu-id="56f56-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="56f56-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="56f56-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="56f56-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="56f56-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="56f56-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
