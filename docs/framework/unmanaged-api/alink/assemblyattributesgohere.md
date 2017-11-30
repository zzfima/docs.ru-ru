---
title: AssemblyAttributesGoHere
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyAttributesGoHere
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9577ecb1f987d86527a96723f45f09509c55d5cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyattributesgohere"></a><span data-ttu-id="bd332-102">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="bd332-102">AssemblyAttributesGoHere</span></span>
<span data-ttu-id="bd332-103">Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.</span><span class="sxs-lookup"><span data-stu-id="bd332-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd332-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd332-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHere  
```  
  
## <a name="remarks"></a><span data-ttu-id="bd332-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd332-105">Remarks</span></span>  
 <span data-ttu-id="bd332-106">Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="bd332-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="bd332-107">При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="bd332-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="bd332-108">Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.</span><span class="sxs-lookup"><span data-stu-id="bd332-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="bd332-109">Ссылки на этот тип указывают пользовательские атрибуты, не связанные с безопасностью, которые нельзя использовать многократно.</span><span class="sxs-lookup"><span data-stu-id="bd332-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="bd332-110">Эти типы помечены как «внутренние» в .NET Framework и находятся в <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="bd332-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd332-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bd332-111">Requirements</span></span>  
 <span data-ttu-id="bd332-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="bd332-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd332-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bd332-113">See Also</span></span>  
 [<span data-ttu-id="bd332-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="bd332-114">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="bd332-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="bd332-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)  
 [<span data-ttu-id="bd332-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="bd332-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
