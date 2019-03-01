---
title: Класс AssemblyAttributesGoHereSM (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b156ed9c318e71a408ea10f2744911a85faedc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975372"
---
# <a name="assemblyattributesgoheresm-class"></a><span data-ttu-id="fa7b3-102">AssemblyAttributesGoHereSM-класс</span><span class="sxs-lookup"><span data-stu-id="fa7b3-102">AssemblyAttributesGoHereSM Class</span></span>

<span data-ttu-id="fa7b3-103">Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.</span><span class="sxs-lookup"><span data-stu-id="fa7b3-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa7b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa7b3-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a><span data-ttu-id="fa7b3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa7b3-105">Remarks</span></span>

<span data-ttu-id="fa7b3-106">Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="fa7b3-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="fa7b3-107">При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="fa7b3-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="fa7b3-108">Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.</span><span class="sxs-lookup"><span data-stu-id="fa7b3-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="fa7b3-109">Ссылки на этот тип указывают пользовательские атрибуты многократного использования, связанные с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="fa7b3-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>

<span data-ttu-id="fa7b3-110">Эти типы помечены как «внутренние» в .NET Framework и находятся в папке <xref:System.Runtime.CompilerServices> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fa7b3-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa7b3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fa7b3-111">Requirements</span></span>

<span data-ttu-id="fa7b3-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="fa7b3-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="fa7b3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fa7b3-113">See also</span></span>

- [<span data-ttu-id="fa7b3-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="fa7b3-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="fa7b3-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="fa7b3-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="fa7b3-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="fa7b3-116">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
