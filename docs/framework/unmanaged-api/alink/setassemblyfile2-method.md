---
title: Метод SetAssemblyFile2
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787215"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="86f3c-102">Метод SetAssemblyFile2</span><span class="sxs-lookup"><span data-stu-id="86f3c-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="86f3c-103">Задает имя параметров и для новой сборки.</span><span class="sxs-lookup"><span data-stu-id="86f3c-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="86f3c-104">Не вызывайте этот метод при создании несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="86f3c-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f3c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86f3c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="86f3c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="86f3c-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="86f3c-107">Имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="86f3c-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="86f3c-108">Интерфейс интерфейса [IMetaDataEmit2](../metadata/imetadataemit2-interface.md) для этого файла.</span><span class="sxs-lookup"><span data-stu-id="86f3c-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="86f3c-109">Параметры, представленные [перечислением AssemblyFlags](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="86f3c-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="86f3c-110">Получает уникальный идентификатор для создаваемой сборки.</span><span class="sxs-lookup"><span data-stu-id="86f3c-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86f3c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86f3c-111">Return Value</span></span>  
 <span data-ttu-id="86f3c-112">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="86f3c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f3c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="86f3c-113">Requirements</span></span>  
 <span data-ttu-id="86f3c-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="86f3c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f3c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="86f3c-115">See also</span></span>

- [<span data-ttu-id="86f3c-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="86f3c-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="86f3c-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="86f3c-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="86f3c-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="86f3c-118">ALink API</span></span>](index.md)
