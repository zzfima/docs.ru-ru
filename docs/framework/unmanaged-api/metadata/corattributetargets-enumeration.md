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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54d239c3091b29424b26fbab4cb4eb9152ff9ad9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442170"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="3cb70-102">Перечисление CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="3cb70-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="3cb70-103">Задает элементы приложения, в которых допустимо применять аргумент.</span><span class="sxs-lookup"><span data-stu-id="3cb70-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cb70-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="3cb70-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3cb70-105">Members</span></span>  
  
|<span data-ttu-id="3cb70-106">Член</span><span class="sxs-lookup"><span data-stu-id="3cb70-106">Member</span></span>|<span data-ttu-id="3cb70-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3cb70-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="3cb70-108">Атрибут может применяться к сборке.</span><span class="sxs-lookup"><span data-stu-id="3cb70-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="3cb70-109">Атрибут может применяться для переносимого исполняемого модуля (.dll или .exe).</span><span class="sxs-lookup"><span data-stu-id="3cb70-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="3cb70-110">Атрибут может применяться к классу.</span><span class="sxs-lookup"><span data-stu-id="3cb70-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="3cb70-111">Атрибут может быть применен к структуре; то есть введите значение.</span><span class="sxs-lookup"><span data-stu-id="3cb70-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="3cb70-112">Атрибут может применяться к перечислению.</span><span class="sxs-lookup"><span data-stu-id="3cb70-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="3cb70-113">Атрибут может применяться для конструктора.</span><span class="sxs-lookup"><span data-stu-id="3cb70-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="3cb70-114">Атрибут может применяться к методу.</span><span class="sxs-lookup"><span data-stu-id="3cb70-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="3cb70-115">Атрибут может применяться к свойству.</span><span class="sxs-lookup"><span data-stu-id="3cb70-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="3cb70-116">Атрибут может применяться к полю.</span><span class="sxs-lookup"><span data-stu-id="3cb70-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="3cb70-117">Атрибут может применяться к событию.</span><span class="sxs-lookup"><span data-stu-id="3cb70-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="3cb70-118">Атрибут может применяться к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="3cb70-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="3cb70-119">Атрибут может применяться к параметру.</span><span class="sxs-lookup"><span data-stu-id="3cb70-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="3cb70-120">Атрибут может применяться к делегату.</span><span class="sxs-lookup"><span data-stu-id="3cb70-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="3cb70-121">Атрибут может применяться для универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="3cb70-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="3cb70-122">Атрибут может применяться к любому элементу приложения.</span><span class="sxs-lookup"><span data-stu-id="3cb70-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="3cb70-123">Атрибут может применяться к члену класса.</span><span class="sxs-lookup"><span data-stu-id="3cb70-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cb70-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cb70-124">Remarks</span></span>  
 <span data-ttu-id="3cb70-125">`CorAttributeTargets` Значения перечисления могут быть объединены с помощью побитовой операции или для получения необходимого сочетания.</span><span class="sxs-lookup"><span data-stu-id="3cb70-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="3cb70-126">`CorAttributeTargets` Параллельно управляемый <xref:System.AttributeTargets?displayProperty=nameWithType> перечисления.</span><span class="sxs-lookup"><span data-stu-id="3cb70-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cb70-127">Требования</span><span class="sxs-lookup"><span data-stu-id="3cb70-127">Requirements</span></span>  
 <span data-ttu-id="3cb70-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cb70-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cb70-129">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3cb70-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3cb70-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cb70-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb70-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3cb70-131">See Also</span></span>  
 [<span data-ttu-id="3cb70-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3cb70-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
