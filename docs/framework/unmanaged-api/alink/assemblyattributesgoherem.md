---
title: Класс AssemblyAttributesGoHereM (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69167fda194e9d916f44751fd1f9dcee92822377
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972393"
---
# <a name="assemblyattributesgoherem-class"></a><span data-ttu-id="25bde-102">AssemblyAttributesGoHereM-класс</span><span class="sxs-lookup"><span data-stu-id="25bde-102">AssemblyAttributesGoHereM Class</span></span>

<span data-ttu-id="25bde-103">Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.</span><span class="sxs-lookup"><span data-stu-id="25bde-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="25bde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25bde-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a><span data-ttu-id="25bde-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="25bde-105">Remarks</span></span>

<span data-ttu-id="25bde-106">Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки.</span><span class="sxs-lookup"><span data-stu-id="25bde-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="25bde-107">При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="25bde-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="25bde-108">Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.</span><span class="sxs-lookup"><span data-stu-id="25bde-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="25bde-109">Ссылки на этот тип указывают пользовательские атрибуты, не связанные с безопасностью, но многократного использования.</span><span class="sxs-lookup"><span data-stu-id="25bde-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>

<span data-ttu-id="25bde-110">Эти типы помечены как «внутренние» в .NET Framework и находятся в папке <xref:System.Runtime.CompilerServices> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="25bde-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="25bde-111">Требования</span><span class="sxs-lookup"><span data-stu-id="25bde-111">Requirements</span></span>

<span data-ttu-id="25bde-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="25bde-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="25bde-113">См. также</span><span class="sxs-lookup"><span data-stu-id="25bde-113">See also</span></span>

- [<span data-ttu-id="25bde-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="25bde-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="25bde-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="25bde-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="25bde-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="25bde-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
