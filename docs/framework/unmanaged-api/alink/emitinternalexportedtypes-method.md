---
title: Метод EmitInternalExportedTypes
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55b9d185804f25c7431f2696d67753cc3ba02d1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402045"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="f4651-102">Метод EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="f4651-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="f4651-103">Выдает типы, добавленные в сборку.</span><span class="sxs-lookup"><span data-stu-id="f4651-103">Emits types added to the assembly.</span></span> <span data-ttu-id="f4651-104">Этот метод Выяснив, что добавлены внутренние типы.</span><span class="sxs-lookup"><span data-stu-id="f4651-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4651-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4651-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4651-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4651-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f4651-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="f4651-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4651-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f4651-108">Return Value</span></span>  
 <span data-ttu-id="f4651-109">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f4651-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4651-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f4651-110">Requirements</span></span>  
 <span data-ttu-id="f4651-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="f4651-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4651-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f4651-112">See Also</span></span>  
 [<span data-ttu-id="f4651-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f4651-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f4651-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f4651-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f4651-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="f4651-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
