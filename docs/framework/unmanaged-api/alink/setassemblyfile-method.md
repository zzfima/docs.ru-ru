---
title: Метод SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76d341aca7c96e5932a1fc155ccaee17ce6585da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776998"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="ecd77-102">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="ecd77-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="ecd77-103">Присваивает имя сборки, которая должна быть построена.</span><span class="sxs-lookup"><span data-stu-id="ecd77-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="ecd77-104">Не предназначен для использования при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="ecd77-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd77-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecd77-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecd77-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecd77-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="ecd77-107">Полное имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="ecd77-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="ecd77-108">Указатель на интерфейс [интерфейса IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ecd77-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="ecd77-109">Флаги, определенные в [перечислении AssemblyFlags](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ecd77-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="ecd77-110">Указатель на идентификатор результирующей сборки.</span><span class="sxs-lookup"><span data-stu-id="ecd77-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecd77-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ecd77-111">Return Value</span></span>  
 <span data-ttu-id="ecd77-112">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="ecd77-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecd77-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ecd77-113">Requirements</span></span>  
 <span data-ttu-id="ecd77-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="ecd77-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd77-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ecd77-115">See also</span></span>

- [<span data-ttu-id="ecd77-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ecd77-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ecd77-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ecd77-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ecd77-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="ecd77-118">ALink API</span></span>](index.md)
