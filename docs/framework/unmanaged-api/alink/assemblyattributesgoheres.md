---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereS
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3506462aaf8d040126d979801460772b3cd47f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706291"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="f77fa-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="f77fa-102">AssemblyAttributesGoHereS</span></span>
<span data-ttu-id="f77fa-103">Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.</span><span class="sxs-lookup"><span data-stu-id="f77fa-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f77fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f77fa-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereS  
```  
  
## <a name="remarks"></a><span data-ttu-id="f77fa-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f77fa-105">Remarks</span></span>  
 <span data-ttu-id="f77fa-106">Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="f77fa-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="f77fa-107">При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f77fa-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="f77fa-108">Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.</span><span class="sxs-lookup"><span data-stu-id="f77fa-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="f77fa-109">Ссылки на этот тип указывают пользовательские атрибуты, связанные с безопасностью, которые нельзя использовать многократно.</span><span class="sxs-lookup"><span data-stu-id="f77fa-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="f77fa-110">Эти типы помечены как «внутренние» в .NET Framework и находятся в <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="f77fa-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f77fa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f77fa-111">Requirements</span></span>  
 <span data-ttu-id="f77fa-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="f77fa-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f77fa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f77fa-113">See also</span></span>
- [<span data-ttu-id="f77fa-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="f77fa-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)
- [<span data-ttu-id="f77fa-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="f77fa-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)
- [<span data-ttu-id="f77fa-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="f77fa-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
