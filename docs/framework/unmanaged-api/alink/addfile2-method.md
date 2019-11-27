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
ms.openlocfilehash: 8dadf9ec8f896b03e4918b21f5153c1b747010fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446667"
---
# <a name="addfile2-method"></a><span data-ttu-id="c4897-102">Метод AddFile2</span><span class="sxs-lookup"><span data-stu-id="c4897-102">AddFile2 Method</span></span>
<span data-ttu-id="c4897-103">Добавляет файлы в сборку.</span><span class="sxs-lookup"><span data-stu-id="c4897-103">Adds files to the assembly.</span></span> <span data-ttu-id="c4897-104">Также можно использовать для создания непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="c4897-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4897-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4897-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4897-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4897-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c4897-107">Идентификатор сборки, в которую добавляется файл.</span><span class="sxs-lookup"><span data-stu-id="c4897-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="c4897-108">Имя добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="c4897-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c4897-109">COM+ `FileDef` флаги, такие как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="c4897-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="c4897-110">`dwFlags` передается в [метод дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="c4897-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c4897-111">Интерфейс для интерфейса интерфейса [IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c4897-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="c4897-112">Получает идентификатор добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="c4897-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4897-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c4897-113">Return Value</span></span>  
 <span data-ttu-id="c4897-114">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c4897-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4897-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c4897-115">Requirements</span></span>  
 <span data-ttu-id="c4897-116">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="c4897-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4897-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4897-117">See also</span></span>

- [<span data-ttu-id="c4897-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c4897-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c4897-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c4897-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c4897-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="c4897-120">ALink API</span></span>](index.md)
