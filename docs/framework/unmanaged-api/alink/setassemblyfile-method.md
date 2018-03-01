---
title: "Метод SetAssemblyFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c0be76e93ab41860f7f3416d0baffe3e4daf84c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="dc53e-102">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="dc53e-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="dc53e-103">Назначает имя сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="dc53e-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="dc53e-104">Не предназначен для использования при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="dc53e-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc53e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc53e-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc53e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc53e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="dc53e-107">Полное имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="dc53e-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="dc53e-108">Указатель на [интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dc53e-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="dc53e-109">Флаги, как определено в [перечисление AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="dc53e-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="dc53e-110">Указатель на идентификатор итоговой сборки.</span><span class="sxs-lookup"><span data-stu-id="dc53e-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc53e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dc53e-111">Return Value</span></span>  
 <span data-ttu-id="dc53e-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="dc53e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc53e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dc53e-113">Requirements</span></span>  
 <span data-ttu-id="dc53e-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="dc53e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc53e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dc53e-115">See Also</span></span>  
 [<span data-ttu-id="dc53e-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="dc53e-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="dc53e-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="dc53e-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="dc53e-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="dc53e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
