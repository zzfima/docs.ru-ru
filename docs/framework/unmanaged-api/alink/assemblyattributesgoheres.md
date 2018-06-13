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
ms.openlocfilehash: d68450d05f667851404a009c0984f8722253e71e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402914"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="b610d-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="b610d-102">AssemblyAttributesGoHereS</span></span>
<span data-ttu-id="b610d-103">Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.</span><span class="sxs-lookup"><span data-stu-id="b610d-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b610d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b610d-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereS  
```  
  
## <a name="remarks"></a><span data-ttu-id="b610d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="b610d-105">Remarks</span></span>  
 <span data-ttu-id="b610d-106">Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="b610d-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="b610d-107">При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b610d-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="b610d-108">Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.</span><span class="sxs-lookup"><span data-stu-id="b610d-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="b610d-109">Ссылки на этот тип указывают пользовательские атрибуты, связанные с безопасностью, которые нельзя использовать многократно.</span><span class="sxs-lookup"><span data-stu-id="b610d-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="b610d-110">Эти типы помечены как «внутренние» в .NET Framework и находятся в <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="b610d-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b610d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b610d-111">Requirements</span></span>  
 <span data-ttu-id="b610d-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="b610d-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b610d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b610d-113">See Also</span></span>  
 [<span data-ttu-id="b610d-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="b610d-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [<span data-ttu-id="b610d-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="b610d-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="b610d-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="b610d-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
