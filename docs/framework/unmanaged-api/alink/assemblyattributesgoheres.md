---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
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
ms.openlocfilehash: 135938c4ed91423145ca46b743620f4236f7f818
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742258"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="8e06a-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="8e06a-102">AssemblyAttributesGoHereS</span></span>

<span data-ttu-id="8e06a-103">Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.</span><span class="sxs-lookup"><span data-stu-id="8e06a-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e06a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e06a-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a><span data-ttu-id="8e06a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e06a-105">Remarks</span></span>

<span data-ttu-id="8e06a-106">Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="8e06a-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="8e06a-107">При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="8e06a-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="8e06a-108">Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.</span><span class="sxs-lookup"><span data-stu-id="8e06a-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="8e06a-109">Ссылки на этот тип указывают пользовательские атрибуты, связанные с безопасностью, которые нельзя использовать многократно.</span><span class="sxs-lookup"><span data-stu-id="8e06a-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>

<span data-ttu-id="8e06a-110">Эти типы помечены как «внутренние» в .NET Framework и находятся в папке <xref:System.Runtime.CompilerServices> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8e06a-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e06a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8e06a-111">Requirements</span></span>

<span data-ttu-id="8e06a-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="8e06a-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="8e06a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8e06a-113">See also</span></span>

- [<span data-ttu-id="8e06a-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="8e06a-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="8e06a-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="8e06a-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="8e06a-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="8e06a-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
