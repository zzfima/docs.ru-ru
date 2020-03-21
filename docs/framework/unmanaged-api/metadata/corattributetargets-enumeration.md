---
title: Перечисление CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176205"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="3ad2a-102">Перечисление CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="3ad2a-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="3ad2a-103">Задает элементы приложения, в которых допустимо применять аргумент.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ad2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ad2a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="3ad2a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3ad2a-105">Members</span></span>  
  
|<span data-ttu-id="3ad2a-106">Участник</span><span class="sxs-lookup"><span data-stu-id="3ad2a-106">Member</span></span>|<span data-ttu-id="3ad2a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3ad2a-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="3ad2a-108">Атрибут может быть применен к сборке.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="3ad2a-109">Атрибут может быть применен к переносному исполняемому (.dll или .exe) модулю.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="3ad2a-110">Атрибут может быть применен к классу.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="3ad2a-111">Атрибут может быть применен к структуре, т.е. может являться типом значения.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="3ad2a-112">Атрибут может быть применен к перечислению.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="3ad2a-113">Атрибут может быть применен к конструктору.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="3ad2a-114">Атрибут может быть применен к методу.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="3ad2a-115">Атрибут может быть применен к свойству.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="3ad2a-116">Атрибут может быть применен к полю.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="3ad2a-117">Атрибут может быть применен к событию.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="3ad2a-118">Атрибут может быть применен к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="3ad2a-119">Атрибут может быть применен к параметру.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="3ad2a-120">Атрибут может быть применен к делегату.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="3ad2a-121">Атрибут может быть применен к универсальному параметру.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="3ad2a-122">Атрибут может быть применен к любому элементу приложения.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="3ad2a-123">Атрибут может быть применен к члену класса.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ad2a-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ad2a-124">Remarks</span></span>  
 <span data-ttu-id="3ad2a-125">Значения `CorAttributeTargets` перечисления могут быть объединены с bitwise или операции, чтобы получить предпочтительную комбинацию.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="3ad2a-126">Параллели `CorAttributeTargets` управляемого <xref:System.AttributeTargets?displayProperty=nameWithType> перечисления.</span><span class="sxs-lookup"><span data-stu-id="3ad2a-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ad2a-127">Требования</span><span class="sxs-lookup"><span data-stu-id="3ad2a-127">Requirements</span></span>  
 <span data-ttu-id="3ad2a-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ad2a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ad2a-129">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3ad2a-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3ad2a-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ad2a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad2a-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3ad2a-131">See also</span></span>

- [<span data-ttu-id="3ad2a-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3ad2a-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
