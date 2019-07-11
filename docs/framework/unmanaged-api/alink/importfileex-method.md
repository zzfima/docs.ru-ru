---
title: Метод ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fcf714cb0c1c1dd59ae2ec56279870c0bb3e1c4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741722"
---
# <a name="importfileex-method"></a><span data-ttu-id="21db1-102">Метод ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="21db1-102">ImportFileEx Method</span></span>
<span data-ttu-id="21db1-103">Импортирует указанную сборку или Непривязанный модуль.</span><span class="sxs-lookup"><span data-stu-id="21db1-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21db1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21db1-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="21db1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21db1-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="21db1-106">Полное имя файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="21db1-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="21db1-107">Необязательное имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="21db1-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="21db1-108">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="21db1-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="21db1-109">Флаги, передаваемые по [метод OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="21db1-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="21db1-110">Получает идентификатор импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="21db1-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="21db1-111">Получает области импорта сборки [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="21db1-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="21db1-112">Имеет значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="21db1-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="21db1-113">Получает число импортированных файлов и/или областей.</span><span class="sxs-lookup"><span data-stu-id="21db1-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21db1-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="21db1-114">Return Value</span></span>  
 <span data-ttu-id="21db1-115">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="21db1-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21db1-116">Требования</span><span class="sxs-lookup"><span data-stu-id="21db1-116">Requirements</span></span>  
 <span data-ttu-id="21db1-117">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="21db1-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21db1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="21db1-118">See also</span></span>

- [<span data-ttu-id="21db1-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="21db1-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="21db1-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="21db1-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="21db1-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="21db1-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
